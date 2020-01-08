---
title: Lync Server 2013：修改預設的檔案傳輸篩選器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>在 Lync Server 2013 中修改預設的檔案傳輸篩選器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

Lync Server 2013 提供通用檔案傳輸篩選器，可在 Lync Server 2013 部署中的下列與檔案相關的活動中封鎖特定類型的檔案：

  - 在立即訊息（IM）交談期間的檔案傳輸要求

  - 使用 Office Live Meeting 2007 用戶端中的講義功能時的檔案上傳和下載

  - 在會議期間進行多媒體播放

視您想要封鎖或允許的檔案類型而定，您可以使用 Lync Server [控制台] 來修改全域篩選器。 如需檔案傳輸篩選的詳細資料，請參閱[在 Lync Server 2013 中設定立即訊息（IM）的檔案傳輸與 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>修改預設的檔案傳輸篩選器

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [ **IM 和目前狀態**]，然後按一下 [檔案**篩選**]。

4.  在 [檔案**篩選**] 頁面上，按兩下 [**全域**篩選器]。

5.  在 [**編輯檔案篩選器**] 中，選取 [**啟用檔案篩選**] 核取方塊。

6.  在 [檔案**傳輸**] 下拉式清單方塊中，按一下 [**全部封鎖**] 或 [**封鎖特定檔案類型**]。

7.  如果您已按一下 [**全部封鎖**]，請跳至步驟9。

8.  如果您按一下 [**封鎖特定檔案類型**]，請執行下列動作：
    
    1.  按一下 [**選取**]，修改您想要封鎖的檔案類型延伸預設清單。
    
    2.  在 [**選取檔案類型**] 中，從 [**檔案類型延伸**] 底下的類別中新增或移除副檔名，以選取您要封鎖或允許的檔案類型。
    
    3.  如果您沒有看到想要封鎖之檔案類型的副檔名，請在 [**新增檔案類型延伸至] 清單**中的文字方塊中輸入副檔名，然後按一下 [**新增**]。
    
    4.  按一下 [確定]****。

9.  按一下 [認可]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定立即訊息（IM）的檔案傳輸與 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[針對特定網站在 Lync Server 2013 中建立新的檔案傳輸篩選器](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[在 Lync Server 2013 中修改預設的 URL 篩選](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

