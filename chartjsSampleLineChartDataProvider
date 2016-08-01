global with sharing class chartMySessions extends chartjsLineChartData implements iChartjsDataProvider {
    global static string getChartjsData(){  
	
	//Being lazy here: will put this into a List later        
	Integer in15_beginner = [SELECT count() FROM Session__c WHERE Level__c = 'Beginner' AND Session_Date__c < NEXT_YEAR];
	Integer in15_intermediate  = [SELECT count() FROM Session__c WHERE Level__c = 'Intermediate' AND Session_Date__c < NEXT_YEAR];
	Integer in15_advanced  = [SELECT count() FROM Session__c WHERE Level__c = 'Advanced' AND Session_Date__c < NEXT_YEAR];
        
        chartjsLineChartData chartjsData = new chartjsLineChartData();
        chartjsData.labels = new list<string>{'Beginner','Intermediate','Advanced'};
        chartjsData.datasets = new list<chartjsDataset>();
        chartjsDataset dataset;
        
        dataset = new chartjsDataset();
        dataset.label = 'Next Year';
        dataset.fillColor = 'rgba(220,220,220,0.2)';
        dataset.strokeColor = 'rgba(220,220,220,1)';
        dataset.pointColor = 'rgba(220,220,220,1)';
        dataset.pointStrokeColor = '#fff';
        dataset.pointHighlightFill = '#fff';
        dataset.pointHighlightStroke = 'rgba(220,220,220,1)';
        dataset.data = new list<integer>{3, 8, 9}; // Example data set of advanced Sessions on the rise for next year
        chartjsData.datasets.add(dataset);
        
        dataset = new chartjsDataset();
        dataset.label = 'This Year';
        dataset.fillColor = 'rgba(151,187,205,0.2)';
        dataset.strokeColor = 'rgba(151,187,205,1)';
        dataset.pointColor = 'rgba(151,187,205,1)';
        dataset.pointStrokeColor = '#fff';
        dataset.pointHighlightFill = '#fff';
        dataset.pointHighlightStroke = 'rgba(151,187,205,1)';
        dataset.data = new list<integer>{in15_beginner, in15_intermediate, in15_advanced};
        chartjsData.datasets.add(dataset);
        
        return JSON.serialize(chartjsData);
    }
}
