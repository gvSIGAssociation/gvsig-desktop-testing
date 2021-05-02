<script>
const query=window.location.search;
const parameters=new URLSearchParams(query);
if( !parameters.has("check") ) {
 parameters.append("check", '<input type="checkbox">');
}
if( !parameters.has("testcode") ) {
 parameters.append("testcode", '{{ include.testcode | default: page.testcode }}');
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
parameters.append("srcpath", '{{ include.srcpath | default: page.srcpath }}');
</script>
<table style="width:100%;">
 <tr>
  <td>{{ include.testcode | default: page.testcode}}</td>
  <td style="width:100%;"></td>
  <td><a href="https://github.com/gvSIGAssociation/gvsig-desktop-testing/blob/master/docs/${srcpath}">Fuente</a></td>
 </tr>
</table>
