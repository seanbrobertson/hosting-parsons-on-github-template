---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Loop Parson Problems
---
# Loop Parson Problems

Complete each problem by dragging and dropping the code into the correct order. Make sure to indent code that is normally indented.


## Problem 1
Click and drag the code into the correct order. The loop should repeat 5 times.

<div id="LoopTest-sortableTrash" class="sortable-code"></div> 
<div id="LoopTest-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="LoopTest-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="LoopTest-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "For row = 1 to 5\n" +
    "	If name = &quot;hello&quot; Then\n" +
    "    	MsgBox(&quot;hello&quot;)\n" +
    "	End If\n" +
    "Next";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "LoopTest-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "LoopTest-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#LoopTest-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#LoopTest-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>


### Example Next Link
[Next](./parsons/example1.html)
