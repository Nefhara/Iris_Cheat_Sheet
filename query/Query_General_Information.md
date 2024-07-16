# Available Tags

- **case: List of case objects**
  - case.name: Name of the case
  - case.description: Description of the case
  - case.open_date: Case open date 
  - case.close_date: Case close date 
  - case.opened_by: User that initially opened     the case 
  - case.for_customer: Customer linked to the case 
  - case.soc_id: SOC ID number linked to the     case 
- **evidences: List of evidence objects**
  - evidence.filename: File name of the evidence 
  - evidence.date_added: Date of registration 
  - evidence.file_hash: Hash of the evidence 
  - evidence.added_by: User who added the evidence
  - evidence.custom_attributes: Custom attributes of the      evidence
- **iocs: List of IOCs objects**
  - ioc.ioc_value: Value of the IOC 
  - ioc.ioc_description: Description of the IOC
  - ioc.ioc_type: Type of IOC 
  - ioc.ioc_tags: Tags linked to the IOC 
  - ioc.custom_attributes: Custom attributes of the IOC
- **notes: List of notes objects**
  - note.note_title: Title of the note 
  - note.note_content: Content of the note 
  - note.note_creationdate: Creation date of the note 
  - note.note_lastupdate: Date of last update 
  - note.custom_attributes: Custom attributes of the      note
- **tasks: List of tasks objects**
  - task.task_title: Title of the task 
  - task.task_description: Description of the task 
  - task.task_open_date: Open date of the task 
  - task.task_last_update: Last update of the task 
  - task.task_close_date: Date of closure 
  - task.task_status: Status of the task 
  - task.task_tags: Task for the tags 
  - task.custom_attributes: Custom attributes of the      task
- **timeline: List of events objects**
  - event.event_title: Title of the event 
  - event.event_content: Content of the event 
  - event.event_raw: Raw content of the event 
  - event.event_date: Date when the event happened      
  - event.event_source: Source of the event 
  - event.category: Category of the event 
  - event.event_tags: Tags of the events 
  - event.last_edited_by: User who last edited the      event 
  - event.assets: List of assets names linked      to the event
  - event.custom_attributes: Custom attributes of the      event



# Loops

##### Standard loops :

```xml
The IOCs of this case are : 
 
{% for ioc in case.iocs %}
    - {{ ioc.ioc_value }}
    - {{ ioc.ioc_description }}
{% endfor %}
```



##### Table loops :

- To use a loop in a table, a `tr` tag needs to be added to the loop and the loop directly integrated in the table. 

```xml
The IOCs of this case are in the following table : 
 
{%tr for ioc in case.iocs %}
    {{ ioc.ioc_value }}
    {{ ioc.type_name }}
    {{ ioc.ioc_description }}
{%tr endfor %}
```

![](..\assets\table.png)



##### Nested loops :

- Loops can be nested. Don't forget to close each loop. 

```xml
{%for ioc in case.iocs %}
 
    Custom attributes of {{ ioc.ioc_value }} :
 
    {% for attribute in ioc.custom_attributes %}
 
        - {{ attribute }}
 
    {% endfor %}
 
{% endfor %}
```

 

# Conditions

#### Standard

- Check if asset is compromised

```xml
{% for asset in assets %} 
 
    {% if asset.compromised %}
        Asset {{ asset.asset_name }} is compromised
    {% endif %}
 
{% endfor %}
```



#### List is not empty

- To check if a list of objects is not empty, use the processor tag `count`. 

```xml
{% if assets|count %} 
    The case has assets
{% endif %}
```



#### Markdown handling

- The case summary and notes are in markdown. A processor tag should thus be added `|markdown`.

```xml
This is an example of summary : 
 
{{ case.description|markdown }}
```



- Loop over notes

```xml
This is an example of recursive notes  : 
 
{% for note in case.notes %}
 
    My note named {{ note.note_title }} : 
    {{ note.note_content|markdown }}
 
{% endfor %}
```