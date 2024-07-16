### QUERY : {{ timeline }}



### MULTIPLE EVENTS IN TABLE [RESULT]

```xml
[{
	'event_id': 1, 
	'event_title': 'Ransomware Detection', 
	'event_in_summary': True, 
	'event_date': datetime.datetime(2024, 7, 11, 22, 0), 
	'event_tz': '+02:00', 
	'event_date_wtz': datetime.datetime(2024, 7, 12, 0, 0), 
	'event_content': "Antiviral Ransomware Detection", 
	'event_tags': '', 
	'event_source': 'Antivirus Logs', 
	'event_raw': '', 
	'custom_attributes': OrderedDict(), 
	'category': 'Impact', 
	'last_edited_by': 'administrator', 
	'event_uuid': UUID('ce5b9f87-3a44-4d63-800b-17e4339f9f93'), 
	'event_in_graph': True, 
	'event_color': None, 
	'event_is_flagged': False, 
	'assets': ['UC002233554466 (Windows - Computer)'], 
	'iocs': [
		{
			'ioc_id': 1, 
			'ioc_value': 'ransom.exe', 
			'ioc_description': 'Executable file launching ransomware', 
			'tlp_name': 'red', 
			'type': 'filename'}]
}]
```