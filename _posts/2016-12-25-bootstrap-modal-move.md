---
layout: post
title: Bootstrap-modal拖动
category: Javascript
---
###Modal move函数
----------------------
	(function(){
        function moveModal($this){
            var $head = $this.find('.modal-header');
            var $dialog = $this.find('.modal-dialog');
            var move = {
                isMove: false,
                left: 0,
                top: 0
            };
            //委托
            console.log('点击的是',$this);
            $this.on('mousemove', function(e){
                if(!move.isMove) return;
                console.log('移动的是', e.target);
                $dialog.offset({
                    top: e.pageY - move.top,
                    left: e.pageX - move.left
                });
            }).on('mouseup', function(e){
                move.isMove = false;
            });
            $head.on('mousedown', function(e){
                move.isMove = true;
                var offset = $dialog.offset();
                move.left = e.pageX - offset.left;
                move.top = e.pageY - offset.top;
            });
        }
        var oldModal = $.fn.modal;
        $.fn.modal = function(o, _r){
            var $this = $(this);
            if(!$this.attr('ifbindmv')){
                $this.attr('isbindmv','1');
                moveModal($this);
            }
            return oldModal.call(this, o, _r);
        }

        ////要拖动的div背景
        //$('#showErr').modal({backdrop: 'static'});
    })();
