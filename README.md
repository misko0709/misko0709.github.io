<html lang="en">

<head>
    <meta charset="utf-8">
    <meta content="width=device-width, initial-scale=1, shrink-to-fit=no" name="viewport">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>CSV to HTML Table</title>
    <meta name="author" content="Derek Eder">
    <meta content="Display any CSV file as a searchable, filterable, pretty HTML table">

    <!-- Bootstrap core CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.2.1/css/bootstrap.min.css" integrity="sha384-GJzZqFGwb1QTTN6wy59ffF1BuGJpLSa9DkKMp0DgiMDm4iYMj70gZWKYbI706tWS"
        crossorigin="anonymous">
    <link rel="stylesheet" href="https://cdn.datatables.net/1.10.19/css/dataTables.bootstrap4.min.css">

</head>

<body>
<h3>  &nbsp; </h3>
<h1> &nbsp;   &nbsp;  Databaza knih</h1>

    <div class="container-fluid">
        <main class="row">
            <div class="col">


                <div id="table-container">
                </div>
            </div>
        </main>
        
    </div>
    <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.2.1/js/bootstrap.bundle.min.js"></script>
    <script src="js/jquery.csv.min.js"></script>
    <script src="https://cdn.datatables.net/1.10.19/js/jquery.dataTables.min.js"></script>
    <script src="https://cdn.datatables.net/1.10.19/js/dataTables.bootstrap4.min.js"></script>
    <script src="js/csv_to_html_table.js"></script>

    <script>
        function format_link(link) {
            if (link)
                return "<a href='" + link + "' target='_blank'>" + link + "</a>";
            else return "";
        }

        CsvToHtmlTable.init({
            csv_path: "data/kniznica.csv",
            element: "table-container",
            allow_download: true,
            csv_options: {
                separator: ",",
                delimiter: '"'
            },
            datatables_options: {
                paging: false
            },
            custom_formatting: [
                [4, format_link]
            ]
        });
    </script>

</body>

</html>
