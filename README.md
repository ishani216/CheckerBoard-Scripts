var isHoldingPiece = false; 

var pieceInHand = {}; 

PickUpPiece = work (component) { 

/Feature chose component. 

$(element).css("border", "1px strong red"); 

/Refresh stateful factors. 

pieceInHand = component; 

isHoldingPiece = genuine; 

} 

DropPieceInHandOnElement = work (targetElement) { 

/Move the old piece to the new area. 

targetElement.className = pieceInHand.className; 

/Get out the old area. 

$(pieceInHand).css("border", "1px strong dark"); 

pieceInHand.className = "cell"; 

/Refresh stateful factors. 

isHoldingPiece = false; 

pieceInHand = {}; 

} 

$(document).ready(function () 

{ 

var cells = $(".cell"); 

var colorCount = 0; 

for (var I = 0; I < cells.length; i++) { 

var cell = $(cells[i]); 

var isDark = colorCount % 2 == 0; 

var isNextRow = (I + 1) % 8 == 0; 

colorCount += isNextRow ? 2 : 1; 

cell.css("background-shading", isDark ? "naval force" : "white"); 

} 

$(".cell").click(function () { 

in the event that (!isHoldingPiece) { 

in the event that ($(this).hasClass("piece")) { 

PickUpPiece(this) 

} 

} 

else { 

DropPieceInHandOnElement(this) 

} 

}); 
