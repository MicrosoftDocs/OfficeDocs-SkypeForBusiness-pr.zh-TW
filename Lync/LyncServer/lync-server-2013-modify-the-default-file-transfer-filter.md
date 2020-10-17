---
title: Lync Server 2013：修改預設檔案傳輸篩選器
description: Lync Server 2013：修改預設檔案傳輸篩選器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8091dfebea87b793c56b9a670cfeeeab15ce6c44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566929"
---
# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>在 Lync Server 2013 中修改預設檔案傳輸篩選器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

Lync Server 2013 提供通用檔案傳輸篩選器，可在 Lync Server 2013 部署內，封鎖下列與檔相關的活動，以封鎖特定類型的檔案：

  - 立即訊息 (IM) 交談期間的檔案傳輸要求

  - 在 Office Live Meeting 2007 用戶端中使用講義功能時的檔案上傳與下載

  - 會議期間的多媒體播放

根據您想要封鎖或允許的檔案類型，您可以使用 Lync Server 控制台修改全域篩選器。 如需有關檔案傳輸篩選的詳細資訊，請參閱 [在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>修改預設檔案傳輸篩選器

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[IM 和目前狀態]** 和 **[檔案篩選]**。

4.  在 **[檔案篩選]** 頁面上，按兩下 **[全域]** 篩選器。

5.  在 **[編輯檔案篩選]** 中，選取 **[啟用檔案篩選]** 核取方塊。

6.  在 **[檔案傳輸]** 下拉式清單方塊中，按一下 **[全部封鎖]** 或 **[封鎖特定檔案類型]**。

7.  如果您按一下 **[全部封鎖]**，請跳至步驟 9。

8.  如果您按一下 **[封鎖特定檔案類型]**，請執行下列動作：
    
    1.  按一下 **[選取]**，以修改您要封鎖之副檔名的預設清單。
    
    2.  在 **[選取檔案類型]** 中選取您要封鎖或允許的檔案類型，作法是從 **[副檔名]** 下的類別新增或移除其副檔名。
    
    3.  如果您未看見所要封鎖的檔案類型副檔名，請在 **[將副檔名新增至清單]** 下的文字方塊中輸入副檔名，然後按一下 **[新增]**。
    
    4.  按一下 **[確定]**。

9.  按一下 **[認可]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[在 Lync Server 2013 中為特定網站建立新的檔案傳輸篩選器](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[在 Lync Server 2013 中修改預設 URL 篩選器](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

