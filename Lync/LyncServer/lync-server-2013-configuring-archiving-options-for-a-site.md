---
title: Lync Server 2013：設定網站的封存選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 818018a742a12a98b019375d9991393b1ddea37f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>在 Lync Server 2013 中設定網站的封存選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

您可以針對這其中的每一個網站，藉由在封存設定中建立和設定選項，以指定要套用至特定網站的封存選項。網站設定優先於全域設定，但僅適用於網站設定中指定的網站。集區設定優先於網站設定

如需有關封存設定如何運作（包括全域、網站及集區設定的階層）的詳細資訊，請參閱規劃檔、部署檔或作業檔中的封存[在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 啟用封存前，應在封存組態中指定所有適當的選項。



</div>

<div>


> [!IMPORTANT]  
> 若要啟用封存，您必須指定封存原則，以控制全域層級的內部和外部通訊的封存，以及在網站和使用者層級（如果適用）進行封存。 如果您設定使用者層級原則，您也必須將使用者原則指派給特定使用者。 如需建立及設定封存原則的詳細資訊，請參閱 Operations 檔中的<A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">管理 Lync Server 2013 中的內部及外部通訊</A>的封存。



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>在網站層級設定封存選項

1.  透過指派至 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 Lync Server 2013 控制台。 如需可用於啟動 Lync Server 2013 控制台之不同方法的詳細資訊，請參閱[Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中 **，按一下 [****監視與**封存]，然後按一下 [封存設定]。

4.  在 **[封存組態]** 頁面上，按一下 **[新增]**，然後按一下 **[站台組態]**。

5.  在 **[選取站台]** 中，選取要設定封存的網站。

6.  在 **[建立新的封存設定]** 的 **[封存設定]** 下拉式清單方塊中，執行下列其中一項作業：
    
      - 若只要啟用立即訊息 (IM) 工作階段的封存，請按一下 **[封存 IM 工作階段]**。
    
      - 若要同時啟用 IM 工作階段和會議的封存，請按一下 **[封存 IM 和 Web 會議工作階段]**。
    
      - 若要停用原則的封存，請按一下 **[停用封存]**。

7.  此外，在 **[建立新的封存設定]** 中，執行下列動作：
    
      - 若要在封存無法使用時封鎖活動，請選取 **[封存失敗時封鎖立即訊息 (IM) 和 Web 會議工作階段]** 核取方塊。
    
      - 若要使用 Microsoft Exchange Server 儲存封存資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。
    
      - 若要啟用資料清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項作業：
        
          - 若要指定在特定天數後進行清除，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。
        
          - 若要限制只清除已匯出的封存資料，請按一下 **[只清除匯出的封存資料]**。

8.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

