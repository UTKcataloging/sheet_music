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
{{'<originInfo>' + if(isBlank(cells['date1'].value), '', '<dateIssued>' + cells['date1'].value + '</dateIssued><dateIssued encoding="edtf" keyDate="yes">' + cells['date1'].value + '</dateIssued>') + if(isBlank(cells['date_range'].value), '', '<dateIssued>' + cells['date_range'].value + '</dateIssued>') + if(isBlank(cells['date_range1'].value), '', '<dateIssued encoding="edtf" point="start" keyDate="yes">' + cells['date_range1'].value + '</dateIssued>') + if(isBlank(cells['date_range2'].value), '', '<dateIssued encoding="edtf" point="end">' + cells['date_range2'].value + '</dateIssued>') + if(isBlank(cells['publication_location'].value), '', '<place><placeTerm' + if(isBlank(cells['location_URI'].value), '', ' valueURI="' + cells['location_URI'].value +'"') + '>') + if(isBlank(cells['publication_location'].value), '', cells['publication_location'].value + '</placeTerm></place>') +
if(isBlank(cells['publisher'].value), '', '<publisher>' + cells['publisher'].value + '</publisher>') + '</originInfo>'}}
{{if(isBlank(cells['first_line'].value), '', '<note type="first line">' + cells['first_line'].value + '</note>')}}
{{if(isBlank(cells['note'].value), '', '<note>' + cells['note'].value + '</note>')}}
<physicalDescription><extent>{{cells['extent'].value}}</extent><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form><internetMediaType>{{cells['format'].value}}</internetMediaType></physicalDescription>
{{if(isBlank(cells['composer'].value), '', '<name' + if(isBlank(cells['composer_URI'].value), '', ' authority="naf" valueURI="' + cells['composer_URI'].value + '"') + '><namePart>' + cells['composer'].value + '</namePart>' + if(isBlank(cells['composer'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/cmp">Composer</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['composer2'].value), '', '<name' + if(isBlank(cells['composer2_URI'].value), '', ' authority="naf" valueURI="' + cells['composer2_URI'].value + '"') + '><namePart>' + cells['composer2'].value + '</namePart>' + if(isBlank(cells['composer2'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/cmp">Composer</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['composer3'].value), '', '<name' + if(isBlank(cells['composer3_URI'].value), '', ' authority="naf" valueURI="' + cells['composer3_URI'].value + '"') + '><namePart>' + cells['composer3'].value + '</namePart>' + if(isBlank(cells['composer3'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/cmp">Composer</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['lyricist'].value), '', '<name' + if(isBlank(cells['lyricist_URI'].value), '', ' authority="naf" valueURI="' + cells['lyricist_URI'].value + '"') + '><namePart>' + cells['lyricist'].value + '</namePart>' + if(isBlank(cells['lyricist'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/lyr">Lyricist</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['lyricist2'].value), '', '<name' + if(isBlank(cells['lyricist2_URI'].value), '', ' authority="naf" valueURI="' + cells['lyricist2_URI'].value + '"') + '><namePart>' + cells['lyricist2'].value + '</namePart>' + if(isBlank(cells['lyricist2'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/lyr">Lyricist</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['arranger'].value), '', '<name' + if(isBlank(cells['arranger_URI'].value), '', ' authority="naf" valueURI="' + cells['arranger_URI'].value + '"') + '><namePart>' + cells['arranger'].value + '</namePart>' + if(isBlank(cells['arranger'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/arr">Arranger</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['illustrator'].value), '', '<name' + if(isBlank(cells['illustrator_URI'].value), '', ' authority="naf" valueURI="' + cells['illustrator_URI'].value + '"') + '><namePart>' + cells['illustrator'].value + '</namePart>' + if(isBlank(cells['illustrator'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/ill">Illustrator</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['performer'].value), '', '<name><namePart>' + cells['performer'].value + '</namePart>' + if(isBlank(cells['performer'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/asn">Associated name</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['performer2'].value), '', '<name><namePart>' + cells['performer2'].value + '</namePart>' + if(isBlank(cells['performer2'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/asn">Associated name</roleTerm></role>') + '</name>')}}
<subject><topic authority="lcsh" valueURI="{{cells['subject1_URI'].value}}">{{cells['subject1'].value}}</topic></subject>
<subject><topic authority="lcsh" valueURI="{{cells['subject2_URI'].value}}">{{cells['subject2'].value}}</topic></subject>
{{if(isBlank(cells['subject3'].value), '', '<subject><topic' + if(isBlank(cells['subject3_URI'].value), '>', ' authority="lcsh" valueURI="' + cells['subject3_URI'].value + '">') + cells['subject3'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject4'].value), '', '<subject><topic' + if(isBlank(cells['subject4_URI'].value), '>', ' authority="lcsh" valueURI="' + cells['subject4_URI'].value + '">') + cells['subject4'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_geographic'].value), '', '<subject><geographic' + if(isBlank(cells['subject_geographic_URI'].value), '>', ' authority="naf" valueURI="' + cells['subject_geographic_URI'].value + '">') + cells['subject_geographic'].value + '</geographic></subject>')}}
{{if(isBlank(cells['subject_name'].value), '', '<subject><name' + if(isBlank(cells['subject_name_URI'].value), '>', ' authority="naf" valueURI="' + cells['subject_name_URI'].value + '">') + '<namePart>' + cells['subject_name'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['language1'].value), '', '<language><languageTerm type="text" authority="iso639-2b">' + cells['language1'].value + '</languageTerm></language>')}}
{{if(isBlank(cells['language2'].value), '', '<language><languageTerm type="text" authority="iso639-2b">' + cells['language2'].value + '</languageTerm></language>')}}
{{if(isBlank(cells['language3'].value), '', '<language><languageTerm type="text" authority="iso639-2b">' + cells['language3'].value + '</languageTerm></language>')}}
<relatedItem displayLabel="Project" type="host"><titleInfo><title>{{cells['digital_collection'].value}}</title></titleInfo></relatedItem>
<typeOfResource>{{cells['type2'].value}}</typeOfResource>
<typeOfResource>{{cells['type1'].value}}</typeOfResource>
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