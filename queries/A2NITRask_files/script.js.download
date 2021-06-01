function msgbox(heading, formContent) {
    html =  '<div id="dynamicModal" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="confirm-modal" aria-hidden="true">';
    html += '<div class="modal-dialog modal-sm">';
    html += '<div class="modal-content">';


        html += '<div class="modal-header" style="padding: 5px;">';
    if(heading !== '') {
        html += '<h4 style="font-size: 17px!important;margin-top: 5px;margin-left: 5px;">' + heading + '</h4>'
    }
        html += '<a class="close" data-dismiss="modal">×</a>';
        html += '</div>';

    html += '<div class="modal-body" style="font-size: 13px;">';
    html += formContent;
    html += '</div>';
    //html += '<div class="modal-footer">';
    //html += '<span class="btn btn-sm btn-primary" data-dismiss="modal">Close</span>';
    //html += '</div>';  // content
    html += '</div>';  // dialog
    html += '</div>';  // footer
    html += '</div>';  // modalWindow
    $('body').append(html);
    $("#dynamicModal").modal();
    $("#dynamicModal").modal('show');

    $('#dynamicModal').on('hidden.bs.modal', function (e) {
        $(this).remove();
    });

}
function scrollToTop() {
    verticalOffset = typeof (verticalOffset) != 'undefined' ? verticalOffset : 0;
    element = $('html');
    offset = element.offset();
    offsetTop = offset.top;
    $('html, body').animate({
        scrollTop: offsetTop
    }, 300, 'linear');
}
function decodeHtml(html) {
    var txt = document.createElement("textarea");
    txt.innerHTML = html;
    return txt.value;
}
function hideModal() {
    // Using a very general selector - this is because $('#modalDiv').hide
    // will remove the modal window but not the mask
    $('.modal.in').modal('hide');
}
function OpenLighteBox(self ,event){
  if (!self || !event) {
    return false;
  }
  event.stopPropagation();
  var url = $(self).attr('data-href');
  $('#modal_light_box').modal('show').find('.image').attr('src', url);
}

function RegisterReplyReaction(user_id,reply_id,reaction){
  if (!reply_id && !reaction)
    return false;

  $('.reactions-box-comment-replay-container-' + reply_id).css('display', 'none');
  $.get(Wo_Ajax_Requests_File(), {f: 'posts', s: 'register_replay_reaction', user_id: user_id, reply_id: reply_id, reaction: reaction}, function (data) {
    if(data.status == 200) {
        $('.replay-reactions-icons-'+reply_id).html(data.reactions);
        $('.replay-status-reaction-'+reply_id).addClass("active-like");
        //$('.r_likes-'+reply_id).html(data.like_lang);
      //post.find("[id^=likes]").text(data.likes);
    } else {
      //post.find("[id^=likes]").text(data.likes);
    }
    if (data.can_send == 1) {
      SendMessages();
    }
  });

}


function load_ajax_emojii(){
    var emojjii = "😀*😁*😂*🤣*😃*😄*😅*😆*😉*😊*😋*😎*😍*😘*😗*😙*😚*🙂*🤗*🤩*🤔*🤨*😐*😑*😶*🙄*😏*😣*😥*😮*🤐*😯*😪*😫*😴*😌*😛*😜*😝*🤤*😒*😓*😔*😕*🙃*🤑*😲*☹️*🙁*😖*😞*😟*😤*😢*😭*😦*😧*😨*😩*🤯*😬*😰*😱*😳*🤪*😵*😡*😠*🤬*😷*🤒*🤕*🤢*🤮*🤧*😇*🤠*🤡*🤥*🤫*🤭*🧐*🤓*😈*👿*👹*👺*💀*👻*👽*🤖*💩*😺*😸*😹*😻*😼*😽*🙀*😿*😾*👶*👧*🧒*👦*👩*🧑*👨*👵*🧓*👴*👲*💅*🤳*💃*🕺*🕴*👫*👭*👬*💑*🤲*👐*🙌*👏*🤝*👍*👎*👊*✊*🤛*🤜*🤞*✌️*🤟*🤘*👌*👈*👉*👆*👇*☝️*✋*🤚*🖐*🖖*👋*🤙*💪*🖕*✍️*🙏*💍*💄*💋*👄*👅*👂*👃*👣*👁*👀*🧠*🗣*👤*👥";
    
    $('.emo-comment-container').html("");
    $.each(emojjii.split('*'), function(key, value) {
        $('.emo-comment-container').append("<span class=\"emoji_holder\" onclick=\"AddEmoToPostInput('"+ value +"');\"><span>"+ value + "</span>");
    });
}

function load_ajax_emojiiAnswer(id){
    var emojjii = "😀*😁*😂*🤣*😃*😄*😅*😆*😉*😊*😋*😎*😍*😘*😗*😙*😚*🙂*🤗*🤩*🤔*🤨*😐*😑*😶*🙄*😏*😣*😥*😮*🤐*😯*😪*😫*😴*😌*😛*😜*😝*🤤*😒*😓*😔*😕*🙃*🤑*😲*☹️*🙁*😖*😞*😟*😤*😢*😭*😦*😧*😨*😩*🤯*😬*😰*😱*😳*🤪*😵*😡*😠*🤬*😷*🤒*🤕*🤢*🤮*🤧*😇*🤠*🤡*🤥*🤫*🤭*🧐*🤓*😈*👿*👹*👺*💀*👻*👽*🤖*💩*😺*😸*😹*😻*😼*😽*🙀*😿*😾*👶*👧*🧒*👦*👩*🧑*👨*👵*🧓*👴*👲*💅*🤳*💃*🕺*🕴*👫*👭*👬*💑*🤲*👐*🙌*👏*🤝*👍*👎*👊*✊*🤛*🤜*🤞*✌️*🤟*🤘*👌*👈*👉*👆*👇*☝️*✋*🤚*🖐*🖖*👋*🤙*💪*🖕*✍️*🙏*💍*💄*💋*👄*👅*👂*👃*👣*👁*👀*🧠*🗣*👤*👥";
    
    $('.emo-comment-container').html("");
    $.each(emojjii.split('*'), function(key, value) {
        $('.emo-comment-container').append("<span class=\"emoji_holder\" onclick=\"AddEmoToPostAnswer("+ id +",'"+ value +"');\"><span>"+ value + "</span>");
    });
}

function load_ajax_emojiiMessages(){
    var emojjii = "😀*😁*😂*🤣*😃*😄*😅*😆*😉*😊*😋*😎*😍*😘*😗*😙*😚*🙂*🤗*🤩*🤔*🤨*😐*😑*😶*🙄*😏*😣*😥*😮*🤐*😯*😪*😫*😴*😌*😛*😜*😝*🤤*😒*😓*😔*😕*🙃*🤑*😲*☹️*🙁*😖*😞*😟*😤*😢*😭*😦*😧*😨*😩*🤯*😬*😰*😱*😳*🤪*😵*😡*😠*🤬*😷*🤒*🤕*🤢*🤮*🤧*😇*🤠*🤡*🤥*🤫*🤭*🧐*🤓*😈*👿*👹*👺*💀*👻*👽*🤖*💩*😺*😸*😹*😻*😼*😽*🙀*😿*😾*👶*👧*🧒*👦*👩*🧑*👨*👵*🧓*👴*👲*💅*🤳*💃*🕺*🕴*👫*👭*👬*💑*🤲*👐*🙌*👏*🤝*👍*👎*👊*✊*🤛*🤜*🤞*✌️*🤟*🤘*👌*👈*👉*👆*👇*☝️*✋*🤚*🖐*🖖*👋*🤙*💪*🖕*✍️*🙏*💍*💄*💋*👄*👅*👂*👃*👣*👁*👀*🧠*🗣*👤*👥";
    
    $('.emo-comment-container').html("");
    $.each(emojjii.split('*'), function(key, value) {
        $('.emo-comment-container').append("<span class=\"emoji_holder\" onclick=\"AddEmoToPostMessage('"+ value +"');\"><span>"+ value + "</span>");
    });
}

function AddEmoToPostMessage(code) {


$('#new-message').val($('#new-message').val() + code);    

   
       
}

function makeid() {
    var text = "";
    var possible = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";

    for (var i = 0; i < 10; i++)
        text += possible.charAt(Math.floor(Math.random() * possible.length));

    return text;
}

function nl2br (str, is_xhtml) {
    var breakTag = (is_xhtml || typeof is_xhtml === 'undefined') ? '<br />' : '<br>';
    return (str + '').replace(/([^>\r\n]?)(\r\n|\n\r|\r|\n)/g, '$1'+ breakTag +'$2');
}

function escapeHTML(string) {
    var pre = document.createElement('pre');
    var text = document.createTextNode( string );
    pre.appendChild(text);
    return pre.innerHTML;
}

function AddEmoToPostInput(code) {


$('#question_textarea').val($('#question_textarea').val() + code);    

   
       
}


function AddEmoToPostAnswer(id,code) {


$('#answer_text'+id).val($('#answer_text'+id).val() + code);    

   
       
}

function textAreaAdjust(o, h, n) {
    if (n == 'lightbox') {
      recording_node = "comm";
    } else {
       o.style.height = h + 'px';
       o.style.height = (5+o.scrollHeight)+"px";
    }
    if (n == 'comm') {
      recording_node = "comm";
    }
}


// Poll Result
$(window).load(function(){
    drawcircles();
});