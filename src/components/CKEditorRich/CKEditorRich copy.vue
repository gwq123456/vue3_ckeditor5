<template>
 <div class="ckeditor-classic-container">
    <CKEditor :editor="ClassicEditor" :config="editorConfig" v-model="editorData" />
  </div>
</template>
<script lang='ts' setup>
import CKEditor5Vue from "@ckeditor/ckeditor5-vue";
// import { CKEditorClassic }  from "@ckeditor/ckeditor5-build-classic";
import { ClassicEditor } from '@ckeditor/ckeditor5-editor-classic';
import { ref } from 'vue';
import { Alignment } from '@ckeditor/ckeditor5-alignment';
import { Autoformat } from '@ckeditor/ckeditor5-autoformat';
import { Bold, Code, Italic, Strikethrough, Subscript, Superscript, Underline } from '@ckeditor/ckeditor5-basic-styles';
import { BlockQuote } from '@ckeditor/ckeditor5-block-quote';
import { CloudServices } from '@ckeditor/ckeditor5-cloud-services';
import { CodeBlock } from '@ckeditor/ckeditor5-code-block';
// import { TableOfContents } from '@ckeditor/ckeditor5-document-outline';
import { Essentials } from '@ckeditor/ckeditor5-essentials';
// import { ExportPdf } from '@ckeditor/ckeditor5-export-pdf';
// import { ExportWord } from '@ckeditor/ckeditor5-export-word';
import { Font } from '@ckeditor/ckeditor5-font';
// import { FormatPainter } from '@ckeditor/ckeditor5-format-painter';
import { Heading } from '@ckeditor/ckeditor5-heading';
import { Highlight } from '@ckeditor/ckeditor5-highlight';
import { HorizontalLine } from '@ckeditor/ckeditor5-horizontal-line';
import { HtmlEmbed } from '@ckeditor/ckeditor5-html-embed';
import { AutoImage,
    Image,
    ImageCaption,
    ImageInsert,
    ImageResize,
    ImageStyle,
    ImageToolbar,
    ImageUpload,
    PictureEditing
} from '@ckeditor/ckeditor5-image';
import { Indent, IndentBlock } from '@ckeditor/ckeditor5-indent';
import { AutoLink, Link, LinkImage } from '@ckeditor/ckeditor5-link';
import { DocumentList, DocumentListProperties } from '@ckeditor/ckeditor5-list';
import { MediaEmbed } from '@ckeditor/ckeditor5-media-embed';
import { Mention } from '@ckeditor/ckeditor5-mention';
import { PageBreak } from '@ckeditor/ckeditor5-page-break';
import { Paragraph } from '@ckeditor/ckeditor5-paragraph';
import { PasteFromOffice } from '@ckeditor/ckeditor5-paste-from-office';
import { RemoveFormat } from '@ckeditor/ckeditor5-remove-format';
import { ShowBlocks } from '@ckeditor/ckeditor5-show-blocks';
// import { SlashCommand } from '@ckeditor/ckeditor5-slash-command';
import { SourceEditing } from '@ckeditor/ckeditor5-source-editing';
// import { SpecialCharacters, SpecialCharactersEssentials } from '@ckeditor/ckeditor5-special-characters';
import { Table, TableCaption, TableCellProperties, TableColumnResize, TableProperties, TableToolbar } from '@ckeditor/ckeditor5-table';
// import { Template } from '@ckeditor/ckeditor5-template';
import { TextTransformation } from '@ckeditor/ckeditor5-typing';
import { WordCount } from '@ckeditor/ckeditor5-word-count';
// import WProofreader from '@webspellchecker/wproofreader-ckeditor5/src/wproofreader';

const CKEditor = CKEditor5Vue.component;
const editorData = ref("<p>Hello World!</p>");
const editorConfig = {
  plugins: [
      Autoformat, BlockQuote, Bold, Heading, Image, ImageCaption, 
      ImageStyle, ImageToolbar, Indent, Italic, Link, DocumentList, MediaEmbed,
      Paragraph, Table, TableToolbar, Alignment, AutoImage, AutoLink,
      CloudServices, Code, CodeBlock, Essentials, 
       Font, Highlight, HorizontalLine,
      HtmlEmbed, ImageInsert, ImageResize, ImageUpload, IndentBlock, 
      LinkImage, DocumentListProperties, Mention, PageBreak, PasteFromOffice,
      PictureEditing, RemoveFormat, ShowBlocks, SourceEditing,Strikethrough, Subscript, Superscript,
      TableCaption, TableCellProperties, TableColumnResize,
      TableProperties,TextTransformation,
      Underline, WordCount
  ],
  toolbar: {
    items: [
        'undo', 'redo',
        '|',
        'showBlocks', 'formatPainter', 'selectAll',
        '|',
        'heading',
        '|',
        'style',
        '|',
        'fontSize', 'fontFamily', 'fontColor', 'fontBackgroundColor',
        '-',
        'bold', 'italic', 'underline',
        {
            label: 'Formatting',
            icon: 'text',
            items: [ 'strikethrough', 'subscript', 'superscript', 'code', '|', 'removeFormat' ]
        },
        '|',
         'horizontalLine', 'pageBreak',
        '|',
        'link', 'insertImage', 'ckbox', 'insertTable', 'tableOfContents', 'insertTemplate',
        {
            label: 'Insert',
            icon: 'plus',
            items: [ 'highlight', 'blockQuote', 'mediaEmbed', 'codeBlock', 'htmlEmbed' ]
        },
        '|',
        'alignment',
        '|',
        'bulletedList',	'numberedList',	'outdent', 'indent',
        '|',
        'sourceEditing'
    ],
    shouldNotGroupWhenFull: true
  },
  
}
</script>
<style lang='less' scoped>

</style>