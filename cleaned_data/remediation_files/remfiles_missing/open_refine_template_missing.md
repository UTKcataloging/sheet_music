# OpenRefine Template for UT Sheet Music Collection (migration) - missing items

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
<titleInfo><title>{{cells["title"].value}}</title></titleInfo>
{{if(isBlank(cells["alternative_title"].value),'', '<titleInfo type="alternative"><title>' + cells['alternative_title'].value + '</title></titleInfo>')}}
{{'<originInfo>' + if(isBlank(cells['date'].value), '', '<dateIssued>' + cells['date'].value + '</dateIssued>') + if(isBlank(cells['date2'].value), '', '<dateIssued encoding="edtf">' + cells['date2'].value + '</dateIssued>') + if(isBlank(cells['publication_location'].value), '', '<place><placeTerm' + if(isBlank(cells['location_URI'].value), '', ' valueURI="' + cells['location_URI'].value +'"') + '>') + if(isBlank(cells['publication_location'].value), '', cells['publication_location'].value + '</placeTerm></place>') +
if(isBlank(cells['publisher'].value), '', '<publisher>' + cells['publisher'].value + '</publisher>') + '</originInfo>'}}
{{if(isBlank(cells['first_line'].value), '', '<note type="first line">' + cells['first_line'].value + '</note>')}}
{{if(isBlank(cells['note'].value), '', '<note>' + cells['note'].value + '</note>')}}
<physicalDescription><extent>{{cells['extent'].value}}</extent><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form><internetMediaType>{{cells['format'].value}}</internetMediaType></physicalDescription>
<relatedItem displayLabel="Project" type="host"><titleInfo><title>{{cells['digital_collection'].value}}</title></titleInfo></relatedItem>
{{if(isBlank(cells['composer'].value), '', '<name><namePart>' + cells['composer'].value + '</namePart>' + if(isBlank(cells['composer'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/cmp">Composer</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['composer2'].value), '', '<name><namePart>' + cells['composer2'].value + '</namePart>' + if(isBlank(cells['composer2'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/cmp">Composer</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['composer3'].value), '', '<name><namePart>' + cells['composer3'].value + '</namePart>' + if(isBlank(cells['composer3'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/cmp">Composer</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['lyricist'].value), '', '<name><namePart>' + cells['lyricist'].value + '</namePart>' + if(isBlank(cells['lyricist'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/lyr">Lyricist</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['lyricist2'].value), '', '<name><namePart>' + cells['lyricist2'].value + '</namePart>' + if(isBlank(cells['lyricist2'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/lyr">Lyricist</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['arranger'].value), '', '<name><namePart>' + cells['arranger'].value + '</namePart>' + if(isBlank(cells['arranger'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/arr">Arranger</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['performer'].value), '', '<name><namePart>' + cells['performer'].value + '</namePart>' + if(isBlank(cells['performer'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/asn">Associated name</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['performer2'].value), '', '<name><namePart>' + cells['performer2'].value + '</namePart>' + if(isBlank(cells['performer2'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/asn">Associated name</roleTerm></role>') + '</name>')}}
<subject><topic authority="lcsh" valueURI="{{cells['subject1_URI'].value}}">{{cells['subject1'].value}}</topic></subject>
<subject><topic authority="lcsh" valueURI="{{cells['subject2_URI'].value}}">{{cells['subject2'].value}}</topic></subject>
{{if(isBlank(cells['subject3'].value), '', '<subject><topic' + if(isBlank(cells['subject3_URI'].value), '>', ' authority="lcsh" valueURI="' + cells['subject3_URI'].value + '">') + cells['subject3'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject4'].value), '', '<subject><topic' + if(isBlank(cells['subject4_URI'].value), '>', ' authority="lcsh" valueURI="' + cells['subject4_URI'].value + '">') + cells['subject3'].value + '</topic></subject>')}}
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