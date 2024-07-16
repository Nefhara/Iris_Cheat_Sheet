### QUERY : {{ assets }}



### MULTIPLE ASSETS IN TABLE [RESULT]

```xml
[{
	'asset_id': 1, 
	'asset_uuid': UUID('a36dc363-8868-441b-80aa-79fcdd9a014b'), 
	'asset_name': 'UC002233554466', 
	'asset_description': 'Ransomware Entry Point', 
	'asset_compromise_status_id': 1, 
	'type': 'Windows - Computer', 
	'analysis_status': 'Started', 
	'date_added': datetime.datetime(2024, 7, 12, 8, 51, 14, 386916), 
	'asset_domain': 'local.com', 
	'asset_ip': '127.0.0.1', 
	'asset_info': '', 
	'asset_tags': '', 
	'custom_attributes': OrderedDict(), 
	'light_asset_description': 'Ransomware Entry Point', 
	'asset_ioc': [
		{
			'ioc_value': 'ransom.exe', 
			'type_name': 'filename', 
			'ioc_description': 'Executable file launching ransomware'}], 
	'asset_compromise_status': 'Compromised'
}]
```