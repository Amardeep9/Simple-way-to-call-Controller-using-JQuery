# Simple-way-to-call-Controller-using-JQuery

<input type=" submit" value="click me" id="btnClick" />

@section scripts{
    <script type="text/javascript">
        $(document).ready(function () {
            $("#btnClick").click(function () {
                var f = {};
                f.url = '@Url.Action("TestFunction","Home")';
                f.type = "POST";
                f.dataType = "json";
                f.data = JSON.stringify({ ID: 123, FName: "AMAR", LName: "RAWAT" });
                f.contentType = "application/json";
                f.success = function (response) {
                    alert("success");
                };
                f.error = function (response) {
                    alert("failed");
                };
                $.ajax(f);
            });
        });
    </script>
}



public JsonResult TestFunction(int ID, string FName, string LName)
        {
            return Json(new
            {
                result = "OK"

            });
        }
