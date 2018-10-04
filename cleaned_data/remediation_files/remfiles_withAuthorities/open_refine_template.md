# OpenRefine Template for UT Sheet Music Collection (migration) following recon work

---

## Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```

## Row Template

```
<mods>
<identifier type="local">{{cells["adminDB"].value}}</identifier>
<identifier type="pid">{{cells['PID'].value}}</identifier>
{{if(isBlank(cells['title'].value), '', '<titleInfo><title>' + cells['title'].value + '</title></titleInfo>')}}
{{if(isBlank(cells['title2'].value), '', '<titleInfo><title>' + cells['title2'].value + '</title></titleInfo>')}}
{{if(isBlank(cells["alternative_title"].value),'', '<titleInfo type="alternative"><title>' + cells['alternative_title'].value + '</title></titleInfo>')}}
{{'<originInfo>' + if(isBlank(cells['date'].value), '', '<dateIssued>' + cells['date'].value + '</dateIssued>') + if(isBlank(cells['date2'].value), '', '<dateIssued encoding="edtf">' + cells['date2'].value + '</dateIssued>') + if(isBlank(cells['publication_location'].value), '', '<place><placeTerm' + if(isBlank(cells['location_URI'].value), '', ' valueURI="' + cells['location_URI'].value +'"') + '>') + if(isBlank(cells['publication_location'].value), '', cells['publication_location'].value + '</placeTerm></place>') +
if(isBlank(cells['publisher'].value), '', '<publisher>' + cells['publisher'].value + '</publisher>') + '</originInfo>'}}
{{if(isBlank(cells['note'].value), '', '<note>' + cells['note'].value + '</note>')}}
<physicalDescription><extent>{{cells['extent'].value}}</extent><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form><internetMediaType>{{cells['format'].value}}</internetMediaType></physicalDescription>
<relatedItem displayLabel="Project" type="host"><titleInfo><title>{{cells['digital_collection'].value}}</title></titleInfo></relatedItem>
{{if(isBlank(cells['name.add'].value), '', '<name' + if(isBlank(cells['name.URI'].value), '', ' authority="naf" valueURI="' + cells['name.URI'].value + '"') + '><namePart>' + cells['name.add'].value + '</namePart>' + if(isBlank(cells['name.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.roleTerm_URI'].value + '">' + cells['name.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.add2'].value), '', '<name' + if(isBlank(cells['name.URI'].value), '', ' authority="naf" valueURI="' + cells['name.URI'].value + '"') + '><namePart>' + cells['name.add2'].value + '</namePart>' + if(isBlank(cells['name.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.roleTerm_URI'].value + '">' + cells['name.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.0.add'].value), '', '<name' + if(isBlank(cells['name.0_URI'].value), '', ' authority="naf" valueURI="' + cells['name.0_URI'].value + '"') + '><namePart>' + cells['name.0.add'].value + '</namePart>' + if(isBlank(cells['name.0.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.0.roleTerm_URI'].value + '">' + cells['name.0.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.0.add2'].value), '', '<name' + if(isBlank(cells['name.0_URI'].value), '', ' authority="naf" valueURI="' + cells['name.0_URI'].value + '"') + '><namePart>' + cells['name.0.add2'].value + '</namePart>' + if(isBlank(cells['name.0.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.0.roleTerm_URI'].value + '">' + cells['name.0.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.1.add'].value), '', '<name' + if(isBlank(cells['name.1_URI'].value), '', ' authority="naf" valueURI="' + cells['name.1_URI'].value + '"') + '><namePart>' + cells['name.1.add'].value + '</namePart>' + if(isBlank(cells['name.1.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.1.roleTerm_URI'].value + '">' + cells['name.1.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.1.add2'].value), '', '<name' + if(isBlank(cells['name.1_URI'].value), '', ' authority="naf" valueURI="' + cells['name.1_URI'].value + '"') + '><namePart>' + cells['name.1.add2'].value + '</namePart>' + if(isBlank(cells['name.1.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.1.roleTerm_URI'].value + '">' + cells['name.1.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.2.add'].value), '', '<name' + if(isBlank(cells['name.2_URI'].value), '', ' authority="naf" valueURI="' + cells['name.2_URI'].value + '"') + '><namePart>' + cells['name.2.add'].value + '</namePart>' + if(isBlank(cells['name.2.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.2.roleTerm_URI'].value + '">' + cells['name.2.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.2.add2'].value), '', '<name' + if(isBlank(cells['name.2_URI'].value), '', ' authority="naf" valueURI="' + cells['name.2_URI'].value + '"') + '><namePart>' + cells['name.2.add2'].value + '</namePart>' + if(isBlank(cells['name.2.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.2.roleTerm_URI'].value + '">' + cells['name.2.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.3.add'].value), '', '<name' + if(isBlank(cells['name.3_URI'].value), '', ' authority="naf" valueURI="' + cells['name.3_URI'].value + '"') + '><namePart>' + cells['name.3.add'].value + '</namePart>' + if(isBlank(cells['name.3.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.3.roleTerm_URI'].value + '">' + cells['name.3.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.3.add2'].value), '', '<name' + if(isBlank(cells['name.3_URI'].value), '', ' authority="naf" valueURI="' + cells['name.3_URI'].value + '"') + '><namePart>' + cells['name.3.add2'].value + '</namePart>' + if(isBlank(cells['name.3.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.3.roleTerm_URI'].value + '">' + cells['name.3.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.4'].value), '', '<name' + if(isBlank(cells['name.4_URI'].value), '', ' authority="naf" valueURI="' + cells['name.4_URI'].value + '"') + '><namePart>' + cells['name.4'].value + '</namePart>' + if(isBlank(cells['name.4.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.4.roleTerm_URI'].value + '">' + cells['name.4.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.5'].value), '', '<name' + if(isBlank(cells['name.5_URI'].value), '', ' authority="naf" valueURI="' + cells['name.5_URI'].value + '"') + '><namePart>' + cells['name.5'].value + '</namePart>' + if(isBlank(cells['name.5.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.5.roleTerm_URI'].value + '">' + cells['name.5.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.6'].value), '', '<name><namePart>' + cells['name.6'].value + '</namePart>' + if(isBlank(cells['name.6.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.6.roleTerm_URI'].value + '">' + cells['name.6.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.7'].value), '', '<name><namePart>' + cells['name.7'].value + '</namePart>' + if(isBlank(cells['name.7.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.7.roleTerm_URI'].value + '">' + cells['name.7.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.8'].value), '', '<name><namePart>' + cells['name.8'].value + '</namePart>' + if(isBlank(cells['name.8.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.8.roleTerm_URI'].value + '">' + cells['name.8.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.9'].value), '', '<name><namePart>' + cells['name.9'].value + '</namePart>' + if(isBlank(cells['name.9.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.9.roleTerm_URI'].value + '">' + cells['name.9.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.10'].value), '', '<name><namePart>' + cells['name.10'].value + '</namePart>' + if(isBlank(cells['name.10.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.10.roleTerm_URI'].value + '">' + cells['name.10.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.11'].value), '', '<name><namePart>' + cells['name.11'].value + '</namePart>' + if(isBlank(cells['name.11.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.11.roleTerm_URI'].value + '">' + cells['name.11.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.12'].value), '', '<name><namePart>' + cells['name.12'].value + '</namePart>' + if(isBlank(cells['name.12.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.12.roleTerm_URI'].value + '">' + cells['name.12.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.13'].value), '', '<name><namePart>' + cells['name.13'].value + '</namePart>' + if(isBlank(cells['name.13.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.13.roleTerm_URI'].value + '">' + cells['name.13.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.14'].value), '', '<name><namePart>' + cells['name.14'].value + '</namePart>' + if(isBlank(cells['name.14.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.14.roleTerm_URI'].value + '">' + cells['name.14.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.15'].value), '', '<name><namePart>' + cells['name.15'].value + '</namePart>' + if(isBlank(cells['name.15.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.15.roleTerm_URI'].value + '">' + cells['name.15.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['name.16'].value), '', '<name><namePart>' + cells['name.16'].value + '</namePart>' + if(isBlank(cells['name.16.roleTerm'].value), '', '<role><roleTerm authority="marcrelator" valueURI="' + cells['name.16.roleTerm_URI'].value + '">' + cells['name.16.roleTerm'].value + '</roleTerm></role>') + '</name>')}}
<subject><topic authority="lcsh" valueURI="{{cells['subject1_URI'].value}}">{{cells['subject1'].value}}</topic></subject>
<subject><topic authority="lcsh" valueURI="{{cells['subject2_URI'].value}}">{{cells['subject2'].value}}</topic></subject>
{{if(isBlank(cells['subject3'].value), '', '<subject><topic' + if(isBlank(cells['subject3_URI'].value), '>', ' authority="lcsh" valueURI="' + cells['subject3_URI'].value + '">') + cells['subject3'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject4'].value), '', '<subject><topic' + if(isBlank(cells['subject4_URI'].value), '>', ' authority="lcsh" valueURI="' + cells['subject4_URI'].value + '">') + cells['subject3'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_name'].value), '', '<subject' + if(isBlank(cells['subject_name_URI'].value), '>', ' authority="naf" valueURI="' + cells['subject_name_URI'].value + '">') + '<name><namePart>' + cells['subject_name'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['language1'].value), '', '<language><languageTerm type="text" authority="iso639-2b">' + cells['language1'].value + '</languageTerm></language>')}}
{{if(isBlank(cells['language2'].value), '', '<language><languageTerm type="text" authority="iso639-2b">' + cells['language2'].value + '</languageTerm></language>')}}
{{if(isBlank(cells['language3'].value), '', '<language><languageTerm type="text" authority="iso639-2b">' + cells['language3'].value + '</languageTerm></language>')}}
<typeOfResource>{{cells['type1'].value}}</typeOfResource>
<typeOfResource>{{cells['type2'].value}}</typeOfResource>
<relatedItem displayLabel="Collection" type="host"><titleInfo><title>{{cells['collection_name'].value}}</title></titleInfo><identifier>{{cells['collection_identifier'].value}}</identifier><location><url>{{cells['ARK'].value}}</url></location></relatedItem>
{{'<location><physicalLocation valueURI="http://id.loc.gov/authorities/names/no2014027633">University of Tennessee, Knoxville. Special Collections</physicalLocation>' + if(isBlank(cells['source'].value), '', '<shelfLocator>' + cells['source'].value + '</shelfLocator>') + '</location>'}}
<recordInfo><recordContentSource valueURI="http://id.loc.gov/authorities/names/n87808088">University of Tennessee, Knoxville. Libraries</recordContentSource></recordInfo>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>
```

## Row Separator

**LEAVE BLANK**

## Suffix

```
</modsCollection>
```