---
title: Lync Server 2013：為特定網站建立新的檔案傳輸篩選器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10e33523c18f323c34ed129616f0e6012a4ebf11
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501930"
---
# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>在 Lync Server 2013 中為特定網站建立新的檔案傳輸篩選器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

除了修改通用檔案傳輸篩選器之外，您還可以針對 Lync Server 2013 部署中的特定網站，設定自訂檔案傳送篩選器。 如需有關檔案傳輸篩選的詳細資訊，請參閱 [在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>若要為特定網站建立檔案傳輸篩選器

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[IM 和目前狀態]** 和 **[檔案篩選]**。

4.  在 [檔案 **篩選** ] 頁面上，按一下 [ **新增**]。

5.  在 [ **選取網站** ] 對話方塊中，按一下您要建立檔案傳輸篩選的網站，然後按一下 **[確定]**。

6.  在 [ **新增檔案篩選器**] 中，按一下 [ **啟用檔篩選** ] 核取方塊。

7.  在 [ **檔案傳輸** ] 下拉式清單方塊中，按一下 [ **全部封鎖** ] 或 [ **封鎖特定檔案類型**]。

8.  如果您按一下 [ **全部封鎖**]，請跳至步驟10。

9.  如果您按一下 **[封鎖特定檔案類型]**，請執行下列動作：
    
    1.  按一下 **[選取]**，以修改您要封鎖之副檔名的預設清單。
    
    2.  在 [ **選取檔案類型** ] 對話方塊中，從 **[副檔名]** 底下的類別中新增或移除副檔名，以選取您要封鎖或允許的檔案類型。
    
    3.  如果您未看見所要封鎖的檔案類型副檔名，請在 **[將副檔名新增至清單]** 下的文字方塊中輸入副檔名，然後按一下 **[新增]**。
    
    4.  按一下 **[確定]**。

10. 按一下 **[認可]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定立即訊息 (IM) 的檔案傳送和 URL 篩選](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[在 Lync Server 2013 中建立新的 URL 篩選，以處理 IM 交談中的超連結](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[在 Lync Server 2013 中修改預設檔案傳輸篩選器](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[在 Lync Server 2013 中修改預設 URL 篩選器](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

