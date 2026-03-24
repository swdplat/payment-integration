
function ImgLoad(e) {
    const defaultImgUrl = "https://image.mycard520.com/mycardweb/image/loader/iconpic.webp";
    $(e).find('img').each(function () {
        //圖片路徑是否存在
        let img = new Image();
        img.src = $(this).prop('src');
        //console.log("src=" + img.src + ",width=" + img.width + ",height=" + img.height);

        if (img.width == 0 || img.width == 0) {
            $(this).attr('src', defaultImgUrl);
            return;
        }

        //圖片載入
        $(this).on('load', function () {
            //console.log("img is load " + $(this).prop('src'));
        }).on('error', function () {
            //console.log("img is error " + $(this).prop('src'));
            $(this).attr('src', defaultImgUrl);
        });
    });
}



