# evernote-dump

Get all of your attachments out of your exported Evernote enex file and include the correct file dates.

Evernote-dump works by streaming the .enex file through a parser so even extremely large .enex files should work.

# Installation

Before running the Evernote.py script be sure to install.

> pip install -r requirements.txt

# Warning

This is extremely in the alpha phase. I did a proof of concept and now I am working more seriously on a cleaner coded version. The proof of concept version can be found in the **alpha** folder.

# Instructions

Run using

> python evernote_dump.py FILE.enex

All attachments found will be output the the "output" folder in the same directory as "Evernote.py"

All the files found in the enex files will be put in the "output" folder

# Road Map

- [x] Export all attachements.
- [ ] Keep the modified dates.
- [x] Keep file names if desired.
- [x] ~~Don't depend on fileMagic since it doesn't play nice~~ Now working correctly.
- [x] Make compatible with different versions of filemagic.
- [x] Make multilingual just for fun.
- [ ] Export actual notes.
  - [ ] Add links to the images that were extracted.
- [ ] Convert notes to mark down.
- [ ] Make compatible with QownNotes.
- [ ] Add more error check to combat human errors
- [x] Get rid of cleanup warning.

# Evernote Enex File Map

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE en-export SYSTEM "http://xml.evernote.com/pub/evernote-export3.dtd">
<en-export export-date="20130730T205637Z" application="Evernote" version="Evernote Mac">
    <note>
        <title>Test Note for Export</title>
        <content>
            <![CDATA[<?xml version="1.0" encoding="UTF-8" standalone="no"?>
            <!DOCTYPE en-note SYSTEM "http://xml.evernote.com/pub/enml2.dtd">
            <en-note style="word-wrap: break-word; -webkit-nbsp-mode: space; -webkit-line-break: after-white-space;">
                Hello, World.
                <div>
                    <br/>
                </div>
                <div>
                    <en-media alt="" type="image/jpeg" hash="dd7b6d285d09ec054e8cd6a3814ce093"/>
                </div>
            </en-note>
            ]]>
        </content>
        <created>20130730T205204Z</created>
        <updated>20130730T205624Z</updated>
        <tag>fake-tag</tag>
        <note-attributes>
            <latitude>33.88394692352314</latitude>
            <longitude>-117.9191355110099</longitude>
            <altitude>96</altitude>
            <author>exomut</author>
        </note-attributes>
        <resource>
            <data encoding="base64">/9j/4AAQSkZJRgABAQAAAQABAAD/4gxYSUNDX1BST0ZJTEUAAQEAAAxITGlubwIQAABtbnRyUkdCIFhZ
            WiAHzgACAAkABgAxAABhY3NwTVNGVAAAAABJRUMgc1JHQgAAAAAAAAAAAAAAAAAA9tYAAQAAAADTLUhQ
            <!-- ... -->
            kfeIGT/+uufk8DpM0gyVjGfmzkgetesnUoTHJ+5Cxn86zmv4/wB75EW+QHAPUH/P9Ky+s1rtrr/wfvOm
            dBSamnq/xPKp/hpLKmS7x4OBjgn6elee6v4OuLJirRSHb/FtyG9s9u1fR0+oTiIRvGq7W4bpisfUGk1C
            GVWtkIyM57n1rfDY+uqigtU76ffZkUsA6iajHZ6v/P8A4B//2Q==</data>
            <mime>image/jpeg</mime>
            <width>1280</width>
            <height>720</height>
            <resource-attributes>
                <file-name>snapshot-DAE9FC15-88E3-46CF-B744-DA9B1B56EB57.jpg</file-name>
				<source-url>www.google.com</source-url>
            	<latitude>33.88394692352314</latitude>
            	<longitude>-117.9191355110099</longitude>
            	<altitude>96</altitude>
				<camera-make>Sharp</camera-make>
				<camera-model>23</camera-model>
				<attachment>true</attachment> #DOUBLE CHECK
				<application-data>Developer place 4K</application-data>

            </resource-attributes>
        </resource>
    </note>
</en-export>
```