---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Why is this not working?
---
# Parsons Practice

## Parsons 1 (Line Based Grader)
Re-arrange the blocks below so they print out "Hello World!"

<div id="p1-sortableTrash" class="sortable-code"></div>
<div id="p1-sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="p1-feedbackLink" value="Get Feedback" type="button" />
    <input id="p1-newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript">
(function() {
  var initial = "print(\"Hello\")\n" +
    "print(\" \")\n" +
    "print(\"World\")\n" +
    "print(\"!\")";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "p1-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": false,
    "x_indent": 50,
    "lang": "en",
    "trashId": "p1-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#p1-newInstanceLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.shuffleLines();
  });
  $("#p1-feedbackLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.getFeedback();
  });
})();
</script>


## Parsons 2 - This is a test
Click and drag the code into the correct order.

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


### Implementation Notes

When you host multiple Parson's problems on a single markdown page, you need to add a unique prefix. You can easily do this in the Codio generator by typing a unique prefix into the "Prefix" textbox and pressing Enter/Return. Then you can simply copy-paste like normal.

If want each problem to be it's own page, you can use relative path links at the bottom of each of your markdown pages as seen below. If you want students to be able to return to previous problems in this format, consider adding previous links or link to a table of contents like page.

### Example Next Link
[Next](./parsons/example1.html)
