[[100 看板-技術追蹤#^uhq5bq]]


<%

  (await tp.system.suggester(

    (item) =>

      item.basename,

      app.vault.getMarkdownFiles().filter(

        file =>

          file.path.startsWith("Note")

        ),

      false,

      "Enter Parent Note")

  ).basename
