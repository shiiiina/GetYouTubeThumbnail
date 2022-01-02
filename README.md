# GetYouTubeThumbnail
bored, made this, use it if u want

# Script
```js


    function submitURL() {
        url = document.getElementById("yt-url").value
        console.log(url)


        if (url.includes('youtube.com') === true) {
            optionOne(url)

        } else if (url.includes('youtu.be') === true) {
            optionTwo(url)

        } else {
            console.log(`Error`)

        }



    }

    async function optionOne(url) {

        if (url.includes('embed')) {

            let testArr2 = url.split('embed/');
            var items = testArr2[1].split('?')

            var maxRes = `https://i3.ytimg.com/vi/${items[0]}/maxresdefault.jpg`
            var hqRes = `https://i3.ytimg.com/vi/${items[0]}/hqdefault.jpg`

            output(hqRes, maxRes)

        } else {

            let testArr = url.split('watch?v=');
            var item = testArr[1].split('?')

            var maxResOne = `https://i3.ytimg.com/vi/${item[0]}/maxresdefault.jpg`
            var hqResTwo = `https://i3.ytimg.com/vi/${item[0]}/hqdefault.jpg`

            output(hqResTwo, maxResOne)

        }

    }

    async function optionTwo(url) {

        let testArr = url.split('youtu.be/');
        var items = testArr[1].split('?')

        var maxRes = `https://i3.ytimg.com/vi/${items[0]}/maxresdefault.jpg`
        var hqRes = `https://i3.ytimg.com/vi/${items[0]}/hqdefault.jpg`

        output(hqRes, maxRes)

    }

    async function output(hqRes, maxRes) {

        highQualityOutput = document.getElementById("hqRes")
        maxResOutput = document.getElementById("maxRes")

        highQualityOutput.value = hqRes
        maxResOutput.value = maxRes



    }


    function myFunction() {
        var copyText = document.getElementById("hqRes");
        copyText.select();
        copyText.setSelectionRange(0, 99999);
        navigator.clipboard.writeText(copyText.value);

        var tooltip = document.getElementById("myTooltip");
        tooltip.innerHTML = "Copied URL";
    }

    function outFunc() {
        var tooltip = document.getElementById("myTooltip");
        tooltip.innerHTML = "Copy to clipboard";
    }

    function myFunction2() {
        var copyText = document.getElementById("maxRes");
        copyText.select();
        copyText.setSelectionRange(0, 99999);
        navigator.clipboard.writeText(copyText.value);

        var tooltip = document.getElementById("myTooltip2");
        tooltip.innerHTML = "Copied URL";
    }

    function outFunc2() {
        var tooltip = document.getElementById("myTooltip2");
        tooltip.innerHTML = "Copy to clipboard";


    }
```
