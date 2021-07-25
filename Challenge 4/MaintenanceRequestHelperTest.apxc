@istest
public with sharing class MaintenanceRequestHelperTest {
    @istest
    public static void BulkTesting(){
        product2 pt2 = new product2(Name = 'tester',Maintenance_Cycle__c = 10, Replacement_Part__c = true);
        
        Database.insert(pt2); 
        
        
        List<case> caseList = new List<case>();
        for(Integer i=0;i<300;i++){
            caseList.add(new case(
                Type = 'Routine Maintenance',
                Status = 'Closed',
                Subject = 'testing',
                Date_Reported__c = Date.today(),
                ProductId = pt2.id
            ));
        }
        if(caseList.size()>0){   
            Database.insert(caseList);
            System.debug(pt2.id);
            System.debug(caseList.size());
        } 
        
        
        List<Equipment_Maintenance_Item__c> newEMI = new List<Equipment_Maintenance_Item__c>();
        for(Integer i=0;i<5;i++){
            newEMI.add(new Equipment_Maintenance_Item__c(
                Equipment__c = pt2.id,
                Maintenance_Request__c = caseList[1].id,
                Quantity__c = 10));
        }
        if(newEmi.size()>0){
            Database.insert(newEmi);
        }
        
        for(case c :caseList){
            c.Subject = 'For Testing';
        } 
        Database.update(caseList);
        Integer newcase = [Select count() from case where ParentId = :caseList[0].id];
        System.assertEquals(1, newcase);
        
    }
    
    @istest 
    public static void positive(){
        product2 pt2 = new product2(Name = 'tester',Maintenance_Cycle__c = 10);
        insert pt2;
        
        Case cParent = new Case(Type = 'Repair',status = 'Closed',Date_Reported__c = Date.today(),
                                ProductId = pt2.id);
        insert cParent;
        Case cChild = new Case(Type = 'Repair',status = 'Closed',Date_Reported__c = Date.today(),
                               ProductId = pt2.id,parentID = cParent.ParentId);
        insert cChild;
        
        cParent.subject = 'child refrecer record';
        update cParent;
        
        Integer newcase = [Select count() from case where ParentId = :cParent.id];
        System.assertEquals(1, newcase);
        
    }
    @istest public static void negetive(){
        product2 pt2 = new product2(Name = 'tester',Maintenance_Cycle__c = 10);
        insert pt2;
        
        Case c = new Case(Type = 'Repair',status = 'New',Date_Reported__c = Date.today(),
                          ProductId = pt2.id);
        insert c;
        
        c.Status = 'Working';
        update c;
        
        
        Integer newcase = [Select count() from case where ParentId = :c.id];
        System.assertEquals(0, newcase);
    }
    
    
    
    
}
