# Idiom | 成語

<p align="center">
  <img src="img.png" alt="Chengyu">
</p>

<section id="main"><div class="container"><div class="row"><div class="col-md-9 left-body"><div class="content page-h1"><div id="emoji-game"><h1><a href="/Game/chengyu">🤔emoji猜成语 </a><div class="pull-right search-form" style='max-width:160px;'><form action="/Game/search" method='get'><div class="input-group"><input type="text" class="form-control input-sm" placeholder="输入关键字如‘飞’" name='keyword'><span class="input-group-btn input-xs"><input type="hidden" name='category' value='chengyu'><input type="hidden" name='cid' value='4'><button class="btn btn-default btn-sm" type="submit">搜索</button></span></div></form></div></h1><div class="page-expand"><div class="ex-up"><table class="table"><tr><td class='text-center page-emoji' width='50%'>名🐪🎍🏔️</td><td class='text-center'  width='50%'><span class="ans-one" >******</span><span class="ans-two hidden" >名落孙山</span></td></tr></table><span class="arrow hidden-xs"><i class="fa fa-arrow-right"></i></span></div><p class="text-center actions1"><a href="javascript:;" class="btn btn-default page-show-ans" data-ans="名落孙山"><i class="fa fa-eye"></i>显示结果</a>&nbsp;&nbsp;<a href="javascript:;" class="btn btn-info page-new-ex" data-cid='4'><i class="fa fa-refresh"></i>新一个</a>&nbsp;&nbsp;<a href="javascript:;" class="btn btn-warning ex-copy"  data-clipboard-text="【名🐪🎍🏔️】

↓↓↓

名落孙山" ><i class="fa fa-copy"></i>复制</a>&nbsp;<a href="javascript:;" class="btn btn-blue" id='convert'>生成截图分享</a></p><p class="actions2 hidden text-left">来源: emojidaquan.com</p><p class="game-qrcode hidden"><img src="/Public/img/qrcode.jpg" alt="emoji大全二维码" width='100'></p></div></div><div class="modal fade" tabindex="-1" role="dialog" id='modal-screen'><div class="modal-dialog" role="document"><div class="modal-content"><div class="modal-header"><button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button><h4 class="modal-title">截图<span class="visible-xs-inline">(长按保存)</span></h4></div><div class="modal-body" style='padding:15px 4px;'><p class='text-center' style='padding:0;'><img src="" id='screen-img' class="img-responsive" style='border:1px solid #ff5e3a'></p></div></div></div></div><br><br><script type="text/javascript">          	$(function(){
          		$('#transfer').remove();
              $('#search').remove();
              $('.page-show-ans').on('click',function(){
                $(this).addClass('disabled');
                if($('.ans-two').hasClass('hidden')){
                  $('.ans-one').addClass('hidden');
                  $(this).addClass('yes').html('<i class="fa fa-eye-slash"></i>隐藏结果');
                  $('.ans-two').removeClass('hidden');
                }else{
                  $('.ans-one').removeClass('hidden');
                  $('.ans-two').addClass('hidden');
                  $(this).removeClass('yes').html('<i class="fa fa-eye"></i>显示结果');
                }
                $(this).removeClass('disabled');
              });
              $('.page-new-ex').on('click',function(){
                $(this).html('<i class="fa fa-refresh"></i>加载...').addClass('disabled');
                var cid=$(this).data('cid');
                var ex_url="/Others/new_ex2";
                var ex_my=$(this);
                $.post(ex_url,{cid:cid},function(data){
                  if(data.status){
                    var copyall=data.emoji+"\r\n-------------\r\n"+data.word;
                    ex_my.parents('p').find('.ex-copy').attr('data-clipboard-text',copyall);
                    $('.page-show-ans').removeClass('yes').html('<i class="fa fa-eye"></i>显示结果');
                    $('.page-emoji').text(data.emoji);
                    ex_my.parents('p').find('.page-show-ans').attr('data-ans',data.word);
                    $('.ans-one').text('******').removeClass('hidden');
                    $('.ans-two').text(data.word).addClass('hidden');
                  }else{
                    alert(data.msg);
                    return false;
                  }
                },'json');
                $(this).html('<i class="fa fa-refresh"></i>新一个').removeClass('disabled');
              });
          	});
            $('#convert').click(function(){
            	$('.search-form').addClass('hidden');
              $('p.game-qrcode').removeClass('hidden');
              $('h1').css('padding-top','20px');
              var ori_html=$('p.actions').html();
              $('p.actions1').addClass('hidden');
              $('p.actions2').removeClass('hidden');
              convert('#emoji-game');
              $('p.actions1').removeClass('hidden');
              $('p.actions2').addClass('hidden');
              $('h1').css('padding-top',0);
              $('p.game-qrcode').addClass('hidden');
              $('.search-form').removeClass('hidden');
            });
            function convert(id) {
                html2canvas(document.querySelector(id)).then(canvas => {
                  if(!imgUrl){
                    var imgUrl = canvas.toDataURL("image/png");
                  }
                  $('#screen-img').attr('src',imgUrl);
                  $('#modal-screen').modal('show');
                });
              }
          </script>
