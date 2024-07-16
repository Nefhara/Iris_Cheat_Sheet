### QUERY : {{ case }}



```xml
{
	'client': 
		{
		'customer_name': 'IRIS_Customer_Name', 
		'customer_description': "IRIS_Customer_Description.", 
		'customer_sla': '', 
		'customer_id': 2, 
		'client_uuid': '7b68cd90-dca3-43e7-a637-f857aa278e68', 
		'creation_date': '2024-07-12T08:45:46.215653', 
		'last_update_date': '2024-07-12T08:45:46.215653', 
		'custom_attributes': OrderedDict()
	}, 
	'owner': 
		{
		'id': 1, 
		'user_name': 'administrator', 
		'user_login': 'administrator', 
		'user_email': 'administrator@localhost'
	}, 
	'classification': 
		{
		'name': 'malicious-code:worm', 
		'name_expanded': 'Malicious-Code: Worm',
		'description': 'Malware that self-replicates and spread itself to other computers in the network without any user interaction;',
		'id': 5,
		'creation_date': '2024-02-05T07:19:22.962261'
	},
	'state': 
		{
		'state_name': 'Open', 
		'state_description': 'Case is open', 
		'state_id': 3, 'protected': True
	}, 
	'tags': [
		{'tag_title': 'ransomware', 'id': 1},
		{'tag_title': 'malware', 'id': 2},
		{'tag_title': 'apt', 'id': 3},
		{'tag_title': 'live_attack', 'id': 4}
	],
	'user': 
		{
		'id': 1, 'user_name': 'administrator', 
		'user_login': 'administrator', 
		'user_email': 'administrator@localhost'
	}, 
	'reviewer': 
		{
		'id': 1, 
		'user_name': 'administrator', 
		'user_login': 'administrator', 
		'user_email': 'administrator@localhost'
	}, 
	'review_status': 
		{
		'id': 5, 
		'status_name': 'Reviewed'
	}, 
	'severity': 
		{
		'severity_id': 5, 
		'severity_name': 'High', 
		'severity_description': 'High'
	}, 
	'status_name': 'unknown', 
	'protagonists': [], 
	'alerts': [], 
	'case_id': 2, 
	'soc_id': 'CSIRT Ticket SOC_002', 
	'client_id': 2, 
	'name': '#2 - [UNCLASSIFIED] [INC001-2024] Customer Location', 
	'description': "Ransomware attack", 
	'open_date': '2024-07-12', 
	'close_date': None, 
	'initial_date': '2024-07-12T08:47:56.878698', 
	'closing_note': None, 
	'user_id': 1, 
	'owner_id': 1, 
	'status_id': 0, 
	'state_id': 3, 
	'custom_attributes': OrderedDict(), 
	'case_uuid': 'b28d10e1-6918-43e2-b066-d01dddc86f70', 
	'classification_id': 5, 
	'reviewer_id': 1, 
	'review_status_id': 5, 
	'severity_id': 5, 
	'modification_history': [HISTORY_MODIFICATION_LIST],
	'note_directories': [1]
}
```