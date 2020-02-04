---
title: Lync Server 2013：在全域層級設定封存選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59ab58cbee3479bff424e7d69d475e1d83fdd3bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a>在 Lync Server 2013 的全域層級設定封存選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

當您在拓撲中新增封存併發布拓撲時，Lync Server 會建立一個全域配置來進行封存。 根據預設，全域配置中不會啟用任何存檔選項。 全域設定會控制為整個部署啟用哪些選項，除非您設定網站或池設定，而這會覆寫全域配置。

如需有關存檔設定的運作方式（包括全域、網站和池設定的階層），請參閱在規劃檔、部署檔或作業檔中的 [ [Lync Server 2013 存檔] 的運作方式](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 在啟用封存前，您應該先在封存配置中指定所有適當的選項。



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a>在全域層級設定封存選項

1.  從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server 2013 [控制台]。 如需可用於啟動 Lync Server 2013 [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。

4.  在 [**存檔**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯封存設定-全域**] 中的 [**存檔設定**] 下拉式清單中，選取下列其中一個封存選項：
    
      - **停用封存**
    
      - **封存 IM 工作階段**
    
      - **封存 IM 與 Web 會議工作階段**

6.  此外，在 [**編輯存檔設定–全域**] 頁面上，執行下列動作：
    
      - 若要在封存無法使用時封鎖活動，請選取 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。
    
      - 若要使用 Microsoft Exchange Server 儲存存檔資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。
    
      - 若要啟用資料清除，請選取 [**啟用 [清除封存資料**] 核取方塊，然後執行下列其中一項操作：
        
          - 若要指定在特定天數後進行清除，請按一下 **[清除匯出的存檔資料]，並儲存在最長持續時間（天數）之後的儲存封存資料**，然後指定天數。
        
          - 若要限制清除以封存已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。

7.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

