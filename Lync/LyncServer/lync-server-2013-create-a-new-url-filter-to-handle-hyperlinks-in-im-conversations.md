---
title: 在 IM 交談中建立新的 URL 篩選來處理超連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f8f9a06dd80f87f2758269ddd2d468aeae2014d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-26_

除了修改全域 URL 篩選器之外，您還可以針對 Lync Server 2013 部署中的個別網站設定自訂 URL 篩選。 如需 URL 篩選的詳細資料，請參閱[在 Lync Server 2013 中設定立即訊息（IM）的檔案傳輸與 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。

<div>

## <a name="to-create-a-new-url-filter"></a>若要建立新的 URL 篩選

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [ **IM 和目前狀態**]，然後按一下 [ **URL 篩選**]。

4.  按一下 [ **URL 篩選**] 頁面上的 [**新增**]。

5.  在 [**選取網站**] 中，按一下您要為其建立 URL 篩選的網站，然後按一下 **[確定]**。

6.  在 [**新增 Url 篩選**] 對話方塊中，選取 [**啟用 url 篩選**] 核取方塊，以啟用網站的 URL 篩選。

7.  若要封鎖內含副檔名的任何活動 URL，且列在 [檔案**類型延伸**] 底下，並在 [**編輯檔案篩選**] 中封鎖，請選取 [以檔案**副檔名封鎖 url** ] 核取方塊。

8.  在 [**超連結前置**詞] 下拉式清單方塊中，按一下與您想要在立即訊息交談中處理 url 的方式相對應的選項。
    
    [**允許] 消息**框可讓您在傳送允許傳送的超連結時，將警告訊息傳送給使用者。

9.  按一下 [認可]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定立即訊息（IM）的檔案傳輸與 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[針對特定網站在 Lync Server 2013 中建立新的檔案傳輸篩選器](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[在 Lync Server 2013 中修改預設的檔案傳輸篩選器](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[在 Lync Server 2013 中修改預設的 URL 篩選](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

