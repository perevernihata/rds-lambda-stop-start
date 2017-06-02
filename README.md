This is lambda package which can start and stop AWS RDS instances. 
You an configure Cloudwatch rule to emit event which stops multiple instaces by theirs ids: 
Example of start event:

```javascript
{
  "instances": ["test-instance-id-1", "test-instance-id-2"],
  "action": "start"
}
```

Example of stop event:

```javascript
{
  "instances": ["test-instance-id-1", "test-instance-id-2"],
  "action": "stop"
}
```

Stopping instance will create RDS snapshot with name in format: "{instanceId}-{day}-{month}-{year}-{ticks}".
