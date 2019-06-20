* 按天生成日志

```go
    client, err := elastic.NewClient(elastic.SetURL("http://localhost:9200/"),
		elastic.SetBasicAuth("admin","admin"), elastic.SetSniff(false))
	if err != nil {
		log.Panic(err)
	}
	hook, err := elogrus.NewElasticHook(client, "localhost", log.InfoLevel, "log_test")
	if err != nil {
		log.Panic(err)
	}
	logrus.AddHook(hook)
```