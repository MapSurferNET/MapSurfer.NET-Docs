### Generating maps using MSNMapGen ###

This tutorial describes how to generate raster (as a single file or tile cache) or vector maps using a console based application called MSNMapGen.

On Windows: 

>%!COMMAND-LINE!% MSNMapGen.exe [Arguments]

On Linux:

>%!COMMAND-LINE!% ./MSNMapGen.sh [Arguments]


#### Arguments ####


<table class="table">
<tbody>
<tr><th>Argument</th><th>Short form</th><th>Description</th><th>Mode</th></tr>
<tr>
<td>-help</td>
<td>-h</td>
<td>Display usage information.</td>
<td></td>
</tr>
<tr>
<td>-map</td>
<td>-m</td>
<td>The path to a file that contains map styles (see <a href="/docs/usermanual/tools/MSNStudio">MapSurfer.NET Studio</a>).</td>
<td>1,2</td>
</tr>
<tr>
<td>-size</td>
<td>-s</td>
<td>The size of a map in pixels. Default value is 256x256.</td>
<td>1</td>
</tr>
<tr>
<td>-output</td>
<td>-o</td>
<td>The path to a file that is being generated. Default value is output.png</td>
<td>1</td>
</tr>
<tr>
<td>-format</td>
<td>-f</td>
<td>The format of a file that is being generated. Default value is image/png. Other possible values are <strong>image/png24</strong>, <strong>image/png8</strong>, <strong>image/pnga</strong>, <strong>image/bmp</strong>, <strong>image/gif</strong>, <strong>image/jpeg</strong>, <strong>image/tiff</strong>.</td>
<td>1</td>
</tr>
<tr>
<td>-renderer</td>
<td>-r</td>
<td>The name of a rendering backend. Possible values are <strong>GDI</strong> and <strong>Cairo</strong>. Default value is GDI. <strong>Note:</strong> Cairo renderer is not supported on Linux yet.</td>
<td>1</td>
</tr>
<tr>
<td>-bbox</td>
<td>-b</td>
<td>The extent of a map region. The coordinates should be in the same projection as the map. Example: -bbox 959125.94,6339502.88, 972540.64,6349038.40</td>
<td>1</td>
</tr>
<tr>
<td>-tilecachegen</td>
<td>-tcg</td>
<td>The path to a file which contains settings for generating a tile cache. This file can be created using <a href="/docs/usermanual/tools/MSNStudio">MapSurfer.NET Studio</a> (see <span>File &gt; Export &gt; Export To Web Format...)<br /></span></td>
<td>2</td>
</tr>
</tbody>
</table>