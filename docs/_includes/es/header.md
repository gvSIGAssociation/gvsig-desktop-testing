<script>
const query=window.location.search;
const parameters=new URLSearchParams(query);
</script>
<table style="width:100%;">
 <tr>
  <td>{{ include.testcode | default: page.testcode}}</td>
  <td style="width:100%;"></td>
  <td><a href="https://github.com/gvSIGAssociation/gvsig-desktop-testing/blob/master/docs/{{ include.srcpath | default: page.srcpath }}">Fuente</a></td>
 </tr>
</table>
