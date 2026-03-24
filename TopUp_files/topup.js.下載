$(document).ready(function () {
    // 點擊 #btn-checkout-next 時
    $('.btn-checkout-next').on('click', function () {
        //未選擇月卡，點下一步會滑動到畫面中間
        var offset = $('.monthlyCard').offset().top;
        var screenHeight = $(window).height();
        var scrollPosition = offset - (screenHeight / 2) + ($('.monthlyCard').outerHeight() / 2);
        $('html, body').animate({
            scrollTop: scrollPosition
        }, 500);
    });



    //讀取畫面隱藏
    setTimeout(function () {
        $('.loading-welcome').fadeOut();
    }, 500);

    function hidden(str, fronLen, endLen) {
        var leg = str.length - frontLen - endLen;
        var xing = "";
        for (var i = 0; i < len; i++) {
            xing += "*";
        }
        return (
            str.substring(0, fronLen) + xing + str.substring(str.length - endLen)
        );
    }
    /*整理到設計系統*/
    //彈窗-更換頭像-選取
    $('.my-modal-body .faceImg-item').click(function () {
        $('.my-modal-body .faceImg-item').not(this).removeClass('click');
        $(this).addClass('click');
        $('.my-modal-footer .my-btn-main').removeClass('my-btn-disabled');
    });

    //Quick-眼睛隱碼
    $('.my-member-quick-points .iconBox').click(function () {
        var $parentContainer = $(this).closest('.swiper-slide');
        $parentContainer.find('.btn-eyeOn').toggleClass('show');
        $parentContainer.find('.btn-eyeOff').toggleClass('show');
    });
    /*整理到設計系統*/

    // 防止點擊radio時觸發兩次點擊事件
    $('.product-column-item input[type="radio"]').click(function (e) {
        e.stopPropagation();
    });

    // // 20241218 開始
    $('.tab-topUp').click(function () {
        $('.checkout').addClass('my-d-none');
        $('.product-column-item').removeClass('active');
    });
    // // 20241218 結束

    //查看詳情跳彈窗
    $('.btn-seemore').on('click', function () {
        $('.product-pup form, .topUpItem-overlay').removeClass('my-d-none');
        $('body').addClass('noslide');
    });

    //遮罩
    $('.topUpItem-overlay').on('click', function () {
        $('.product-pup form,.event-pup .my-modal,.systemMsg-pup .my-modal, .topUpItem-overlay').addClass('my-d-none');
        $('body').removeClass('noslide');
    });

    $('.my-modal-close').on('click', function () {
        $('.product-pup form, .event-pup .my-modal,.systemMsg-pup .my-modal, .topUpItem-overlay').addClass('my-d-none');
        $('body').removeClass('noslide');
    });

    // 彈窗-虛寶收合
    $('.my-modal-body .textBox-imgText-list-item').each(function () {
        // 如果有icon才顯示游標狀態
        if ($(this).find('.textBox-imgText-list-item-icon').length > 0) {
            $(this).addClass('cursor');
        }
    });

    // 點擊事件統一處理
    function toggleList(item) {
        // 收起其他列表並重置圖示
        $('.my-modal-body .textBox-imgText-list-item').not(item).find('.textBox-imgText-list').slideUp(300);
        $('.my-modal-body .textBox-imgText-list-item').not(item).find('.textBox-imgText-list-item-icon svg').removeClass('rotate-180');

        // 切換當前列表與圖示旋轉狀態
        $(item).find('.textBox-imgText-list').slideToggle(300);
        $(item).find('.textBox-imgText-list-item-icon svg').toggleClass('rotate-180');
    }

    // 點擊 .textBox-imgText-list-item
    $('.my-modal-body .textBox-imgText-list-item').click(function (e) {
        const targetSvg = $(e.target).closest('.textBox-imgText-list-item-icon svg');
        if (targetSvg.length > 0) {
            // 點擊的是圖示，直接收合其他並切換當前
            toggleList($(this));
            return;
        }
        // 點擊的是其他地方
        toggleList(this);
    });

    // 20241221
    document.querySelectorAll('.textBox-imgText-list-item-text.my-text-secondary-400').forEach(span => {
        // 阻止點擊事件冒泡
        span.addEventListener('click', event => {
            event.stopPropagation();
        });

        // 設定滑鼠指標樣式
        span.style.cursor = 'auto';
    });

    //介紹查看更多
    $('.btn-more').click(function () {
        // 切換父元素 .text 下的 .textBox 的 .heightLimit 類
        $(this).closest('.text').find('.textBox').toggleClass('heightLimit');

        // 切換 .iconBox 的 rotate-180 類
        $(this).find('.iconBox').toggleClass('rotate-180');

        //// 切換按鈕文字
        //var $textSpan = $(this).find('span.textBox');
        //if ($textSpan.text() === '顯示更多') {
        //    $textSpan.text('收起更多');
        //} else {
        //    $textSpan.text('顯示更多');
        //}
    });

    //活動 查看詳情彈窗
    // 20241008
    $(".my-btn-main-text .eventItem-btn,.my-btn-main-text .my-btn-arrow,.btn-question").click(function () {
        $(this).closest('.eventItem')
            .find(".event-pup .my-modal")
            .removeClass("my-d-none");
        // If you want to keep the overlay functionality:
        $(".topUpItem-overlay").removeClass("my-d-none");
        $('body').addClass('noslide');
    });

    // 20240923
    $(".btn-seemore,.my-modal-close,.information a.my-btn-main-text,.btn-question").click(function (e) {
        if (!$('.my-overlay').is(':visible')) { // 檢查 overlay 是否可見
            // $('.overlay').toggle();
            $('body').addClass('noslide');
        }
    });
    $(".my-overlay,.my-modal-close,.my-btn-main-text").click(function () {
        $('body').removeClass('noslide');
    });

    $("a.my-btn-main-text,.btn-question").click(function () {
        $('body').addClass('noslide');
    });
});

// 20241218 結束
document.addEventListener('scroll', function () {
    const checkout = document.querySelector('.checkout');
    const userSelectProduct = document.querySelector('.user-selectPayment');

    if (!checkout || !userSelectProduct) return; // 確保元素存在

    // 取得 .user-selectPayment 與視窗底部的位置
    const userSelectProductBottom = userSelectProduct.getBoundingClientRect().bottom;
    const viewportHeight = window.innerHeight;

    // 判斷是否需要添加或移除 .fixed-bottom
    if (userSelectProductBottom <= viewportHeight - 200 && checkout.classList.contains('fixed-bottom')) {
        checkout.classList.remove('fixed-bottom'); // .user-selectPayment 底部距離視窗底部 -200px 或更少時移除 .fixed-bottom
    } else if (userSelectProductBottom > viewportHeight - 200 && !checkout.classList.contains('fixed-bottom')) {
        checkout.classList.add('fixed-bottom'); // .user-selectPayment 底部未到達視窗底部 -200px 時添加 .fixed-bottom
    }
});