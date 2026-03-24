// JavaScript Document

$(document).ready(function(){

	"use strict";

	$(".member_menu_accordion").accordion({
		collapsible:true,
		heightStyle:"content"
	});

	var member_menu_accordion = $(".member_menu_accordion h3");
	
	member_menu_accordion.click(function(){
		if($(this).hasClass("active")){
			member_menu_accordion.removeClass("active");
		}else{
			member_menu_accordion.removeClass("active");
			$(this).addClass("active");		
		}
	});
	
	var member_menu_width = $('#member_menu').width();
	
	$('.menu_switch').toggle(
		function(){$('#member_menu').animate({'left': '0'});},
		function(){$('#member_menu').animate({'left': -member_menu_width+'px'});}
	);

	$('#member_menu').mouseover(function() {
		if($('#member_menu').css('left') === -member_menu_width+'px'){
			$('#member_menu').animate({'left': -member_menu_width+10+'px'});
		}
	});
	
	$('#member_menu').mouseleave(function() {
		if($('#member_menu').css('left') === -member_menu_width+10+'px'){
			$('#member_menu').animate({'left':-member_menu_width+'px'});
		}
	});
	
	$('.m_quick').click(function(){
		$('#member_menu').fadeIn();
	});
	
	$('.close_member_menu').click(function(){
		$('#member_menu').fadeOut();
	});

});