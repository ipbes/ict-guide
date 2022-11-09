# Zotero administration

### Reference workflow

<figure><img src="../../.gitbook/assets/references-flow_zotero.jpg" alt=""><figcaption><p>Reference workflow</p></figcaption></figure>

1. The technical support units will be required to clean references stored in Zotero periodically. Experts will only have read only access when this is taking place
2. Experts are strongly encouraged to import references into Zotero using the Zotero web tool or by importing .ris and .bib files. Dragging of PDF files is discourgaged
3. File sharing through Zotero is possible. Preference should be on grey literature. DOI of other files will suffice.

### Archiving a library

To export an entire library, right-click on it in the Zotero collections pane and choose “Export Library…”, or select “Export Library…” from the “File” menu. To export an individual collection, right-click on it and choose “Export Collection…”. To export specific items, select them in the items list, right-click, and choose “Export Items…”.

When sharing items with another Zotero user, select Zotero RDF with files and notes for the most complete transfer.

<figure><img src="../.gitbook/assets/zotero_export_library.jpg" alt=""><figcaption><p>Exporting an entire library</p></figcaption></figure>

<figure><img src="../.gitbook/assets/zotero_export_library_format_zoterordf2%20(1).jpg" alt=""><figcaption><p>Select format (Zotero RDF) including notes, files and annotations</p></figcaption></figure>

### Deleting multiple attachments

Deleting multiple attachments requires the creation of a "Saved Search". This can be used for deleting notes or PDFs or anything that meets a specified criteria.

1. Do an advanced search for "Attachment FIle Type --is --- PDF"

<figure><img src="../.gitbook/assets/Screenshot%202022-09-15%20at%2008.50.50.png" alt=""><figcaption><p>Advanced search</p></figcaption></figure>

1. Create a saved search

<figure><img src="../.gitbook/assets/Screenshot%202022-09-15%20at%2008.52.27.png" alt=""><figcaption><p>Select "Attachment File Type" is "PDF" and then click on "Save Search"</p></figcaption></figure>

1. Navigate to the saved search and select all (ctrl+a or cmd+a on a mac) and the right-click on "move items to trash".

{% hint style="info" %}
The saved search will also contain the items to which the PDFs are attached, select all will only select the attachments.
{% endhint %}

<figure><img src="../.gitbook/assets/Screenshot%202022-09-15%20at%2009.03.58.png" alt=""><figcaption><p>Navigate to your Saved Search and select all attachments</p></figcaption></figure>

### Workflow to clean and finalize libraries

Please use this workflow when the assessment has been approved and there will be no further changes to the references included in the text.

1. Archive the entire library before you start making any changes. Refer to instructions above on "[Archiving a library](zotero.md#archiving-a-library)"
2. In the Zotero chapter library, select one entry that was used in the chapter and create a tag named "assessment-chapterX". It is recommended to have a unique tag for each chapter. This will allow the determination of where and how frequent citations are used.
3. The bottom left of your screen shows all the tags in your library. Right click on the "assessment-chapterX" tag you just created. Click "Assign color". A pop up window will appear, ensure that the position is selected as 1 and press "Set Color". Assign a color for each of the chapter tags you created in #2.
4. Now, go to this website: [https://rintze.zelle.me/ref-extractor/](https://rintze.zelle.me/ref-extractor/). Select "Choose File" and navigate to the chapter file, and click open
5. Next, under the results section, press the "Select in Zotero button". Here you will see in which libraries the references are located. Select the chapter library which contains the references
6. Click "open Zotero" in the pop up window. Zotero should now open with all the citations used selected
7. Press 1 (or the number corresponding to the position of the tag as set in #3) . Now all used citations used in the chapter document are tagged
8. Simply go through all the entries not tagged and delete them from the library. You will be left with only the tagged references that were used in the document
9. Remove all tags created by automatically and by experts. you should start by deleting tags that were automatically created.

<figure><img src="../.gitbook/assets/image%20(40).png" alt=""><figcaption><p>Delete Automatic Tags in This Library</p></figcaption></figure>

Once you have finalized the clean up of the library you should change the library settings to limit modifications. The library "Group Type" should then be made public.

<figure><img src="../.gitbook/assets/image%20(39).png" alt=""><figcaption><p>Library settings at the end of an assessment. Only group admins can add,edit or remove items or files</p></figcaption></figure>

### Useful plugins

Zotero plugins:

* Search for DOI: [https://github.com/bwiernik/zotero-shortdoi](https://github.com/bwiernik/zotero-shortdoi)

Parse references from CSV: [https://anystyle.io/](https://anystyle.io/)

Search for DOI from citations: [https://doi.crossref.org/simpleTextQuery](https://doi.crossref.org/simpleTextQuery)
