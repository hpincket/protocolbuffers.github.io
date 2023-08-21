+++
title = "csharp_generator.h"
toc_hide = "true"
linkTitle = "C++"
description = "This section contains reference documentation for working with protocol buffer classes in C++."
type = "docs"
+++

<p><code>#include &lt;google/protobuf/compiler/csharp/csharp_generator.h&gt;<br>namespace <a href="#google.protobuf.compiler">google::protobuf::compiler::csharp</a></code></p><p>Generates C# code for a given .proto file. </p><table width="100%"><tr><th colspan="2"><h3 style="margin-top: 4px">Classes in this file</h3></th></tr><tr><td><div><code><a href="#Generator">Generator</a></code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;"><a href='google.protobuf.compiler.code_generator#CodeGenerator'>CodeGenerator</a> implementation which generates a C# source file and header. </div></td></tr></table><h2 id="Generator">class Generator: public <a href="google.protobuf.compiler.code_generator#CodeGenerator">CodeGenerator</a></h2><p><code>#include &lt;<a href="#">google/protobuf/compiler/csharp/csharp_generator.h</a>&gt;<br>namespace <a href="#google.protobuf.compiler">google::protobuf::compiler::csharp</a></code></p><p><a href='google.protobuf.compiler.code_generator#CodeGenerator'>CodeGenerator</a> implementation which generates a C# source file and header. </p><p>If you create your own protocol compiler binary and you want it to support C# output, you can do so by registering an instance of this <a href='google.protobuf.compiler.code_generator#CodeGenerator'>CodeGenerator</a> with the <a href='google.protobuf.compiler.command_line_interface#CommandLineInterface'>CommandLineInterface</a> in your main() function. </p>

<table><tr><th colspan="2"><h3 style="margin-top: 4px">Members</h3></th></tr><tr><td style="border-right-width: 0px; text-align: right;"><code></code></td><td style="border-left-width: 0px"id="Generator.Generator"><div style="padding-left: 16px; text-indent: -16px"><code><b>Generator</b>()</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code></code></td><td style="border-left-width: 0px"id="Generator.~Generator"><div style="padding-left: 16px; text-indent: -16px"><code><b>~Generator</b>()</code></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>virtual bool</code></td><td style="border-left-width: 0px"id="Generator.Generate"><div style="padding-left: 16px; text-indent: -16px"><code><b>Generate</b>(const <a href='google.protobuf.descriptor#FileDescriptor'>FileDescriptor</a> * file, const std::string &amp; parameter, <a href='google.protobuf.compiler.code_generator#GeneratorContext'>GeneratorContext</a> * generator_context, std::string * error) const</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Generates code for the given proto file, generating one or more files in the given output directory.  <a href="#Generator.Generate.details">more...</a></div></td></tr><tr><td style="border-right-width: 0px; text-align: right;"><code>virtual uint64_t</code></td><td style="border-left-width: 0px"id="Generator.GetSupportedFeatures"><div style="padding-left: 16px; text-indent: -16px"><code><b>GetSupportedFeatures</b>() const</code></div><div style="font-style: italic; margin-top: 4px; margin-left: 16px;">Implement this to indicate what features this code generator supports.  <a href="#Generator.GetSupportedFeatures.details">more...</a></div></td></tr></table> <hr><h3 id="Generator.Generate.details"><code>virtual bool Generator::Generate(<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;const <a href='google.protobuf.descriptor#FileDescriptor'>FileDescriptor</a> * file,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;const std::string &amp; parameter,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href='google.protobuf.compiler.code_generator#GeneratorContext'>GeneratorContext</a> * generator_context,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;std::string * error) const</code></h3><div style="margin-left: 16px"><p>Generates code for the given proto file, generating one or more files in the given output directory. </p><p>A parameter to be passed to the generator can be specified on the command line. This is intended to be used to pass generator specific parameters. It is empty if no parameter was given. ParseGeneratorParameter (below), can be used to accept multiple parameters within the single parameter command line flag.</p>
<p>Returns true if successful. Otherwise, sets *error to a description of the problem (e.g. "invalid parameter") and returns false. </p>
</div> <hr><h3 id="Generator.GetSupportedFeatures.details"><code>virtual uint64_t Generator::GetSupportedFeatures() const</code></h3><div style="margin-left: 16px"><p>Implement this to indicate what features this code generator supports. </p><p>This should be a bitwise OR of features from the Features enum in plugin.proto. </p>
</div>