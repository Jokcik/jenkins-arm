##Jenkins ARM + Plugins
Tested on Raspberri Pi4

### Список плагинов на jenkins
```bash
List<String> jenkinsPlugins = new ArrayList<String>(Jenkins.instance.pluginManager.plugins);
jenkinsPlugins.sort { it.shortName }
              .each { plugin ->
                   println ("${plugin.shortName}:${plugin.version}")
              }
```

```bash
docker cp plugins.txt myjenkins:/usr/share/jenkins/ref/plugins.txt
docker exec myjenkins bash -c "/usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt"
```

Связь проекта c докером:
```bash
ln -s $(docker volume inspect --format '{{ .Mountpoint }}' jenkins-arm_jenkins_data) /var/jenkins_home
```
