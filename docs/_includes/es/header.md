<script>
const query=window.location.search;
const parameters=new URLSearchParams(query);
if( !parameters.has("UnknownOkError") ) {
  // https://www.w3schools.com/charsets/ref_utf_dingbats.asp
  parameters.append("UnknownOkError", '<select><option value="unknown">&#10068;</option><option value="ok">&#9989;</option><option value="error">&#10071;</option></select>');
}
if( !parameters.has("check") ) {
 parameters.append("check", '<input type="checkbox">');
}
if( !parameters.has("testcode") ) {
 parameters.append("testcode", '{{ include.testcode | default: page.testcode }}');
}
if( !parameters.has("plancode") ) {
 parameters.append("plancode", '{{ include.plancode | default: page.plancode }}');
}
if( !parameters.has("proccode") ) {
 parameters.append("proccode", '{{ include.proccode | default: page.proccode }}');
}
if( !parameters.has("title") ) {
 parameters.append("title", '{{ include.title | default: page.title }}');
}
if( !parameters.has("srcpath") ) {
 parameters.append("srcpath", '{{ include.srcpath | default: page.srcpath }}');
}
</script>
<table style="width:100%;">
 <tr>
  <td>{{ include.proccode | default: page.proccode | include.testcode | default: page.testcode | include.plancode | default: page.plancode}}</td>
  <td style="width:100%;"></td>
  <td><a href="https://github.com/gvSIGAssociation/gvsig-desktop-testing/blob/master/docs/{{ include.srcpath | default: page.srcpath }}">Fuente</a></td>
 </tr>
</table>
