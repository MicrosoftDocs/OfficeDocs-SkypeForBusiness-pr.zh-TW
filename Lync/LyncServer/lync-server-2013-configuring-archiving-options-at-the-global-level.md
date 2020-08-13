---
title: Lync Server 2013：設定全域層級的封存選項
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
ms.openlocfilehash: 3798d64ba8a2252058756b04b51481e90bdf95c5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a>在 Lync Server 2013 中設定全域層級的封存選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

當您將封存新增至拓撲併發行拓撲時，Lync Server 會建立通用設定進行封存。 根據預設，全域設定中不會啟用任何封存選項。 全域設定會控制針對整個部署啟用哪些選項，除非您設定的網站或集區設定會覆寫全域設定。

如需有關封存設定如何運作（包括全域、網站及集區設定的階層）的詳細資訊，請參閱規劃檔、部署檔或作業檔中的封存 [在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md) 。

<div>


> [!NOTE]  
> 啟用封存前，應在封存組態中指定所有適當的選項。



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a>在全域層級設定封存選項

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 Lync Server 2013 控制台。 如需可用於啟動 Lync Server 2013 控制台之不同方法的詳細資訊，請參閱 [Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中 **，按一下 [****監視與**封存]，然後按一下 [封存設定]。

4.  **在 [封存**設定] 頁面上，依序按一下 [**全域**]、[**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [ **編輯封存設定-全域**] 的 [封存 **設定** ] 下拉式清單中，選取下列其中一個封存選項：
    
      - **停用封存**
    
      - **封存 IM 工作階段**
    
      - **封存 IM 和 Web 會議工作階段**

6.  此外，在 [ **編輯封存設定–通用** ] 頁面上，執行下列動作：
    
      - 若要在封存無法使用時封鎖活動，請選取 **[封存失敗時封鎖立即訊息 (IM) 和 Web 會議工作階段]** 核取方塊。
    
      - 若要使用 Microsoft Exchange Server 儲存封存資料，請按一下 [ **Microsoft exchange 整合** ] 核取方塊。
    
      - 若要啟用資料清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項作業：
        
          - 若要指定在特定天數後進行清除，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。
        
          - 若要限制只清除已匯出的封存資料，請按一下 **[只清除匯出的封存資料]**。

7.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

