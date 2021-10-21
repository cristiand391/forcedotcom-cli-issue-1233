### Create scratch org

`sfdx force:org:create -f config/project-scratch-def.json -s -a issue-1233 -v $DEVHUBUSERNAME --durationdays=1`

### Deploy project

`sfdx force:source:deploy -x package.xml`

### Add custom field translation

Enable translations
Setup > Translation workbench > Add spanish as supported lang

Setup > Translation workbench > Translate : 
Lang: spanish
Setup component: Custom field
Object: Activity
Aspect: Field label

Click on "Field label translation" and add a translation, then Save.

### Retrieve translation

```
sfdx force:source:retrieve --metadata=CustomObjectTranslation:Activity-es

ERROR running force:source:retrieve:  Metadata API request failed: Component conversion failed: Unexpected child metadata [/Users/cdominguez/code/gh/forcedotcom-cli-issue-1233/force-app/main/default/objectTranslations/Activity-es/CallDate__c.fieldTranslation-meta.xml] found for parent type [CustomObjectTranslation]
```
