---
title: Lync Server 2013：配置網站的封存選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14b0e29a2796c23c13a16bfb3e8a202a0a535aaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>在 Lync Server 2013 中設定網站的存檔選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

您可以在每個網站的存檔設定中建立及設定選項，來指定要套用到特定網站的存檔選項。 網站設定會覆寫全域配置，但僅適用于網站設定中指定的網站。 池配置會覆寫網站配置

如需有關存檔設定的運作方式（包括全域、網站和池設定的階層），請參閱在規劃檔、部署檔或作業檔中的 [ [Lync Server 2013 存檔] 的運作方式](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 在啟用封存前，您應該先在封存配置中指定所有適當的選項。



</div>

<div>


> [!IMPORTANT]  
> 若要啟用封存，您必須指定封存原則，以控制全域階層的內部與外部通訊（如果適用的話）與網站和使用者層級的存檔。 如果您設定使用者層級原則，您也必須將使用者原則指派給特定的使用者。 如需建立及設定封存原則的詳細資料，請參閱在作業檔中<A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">管理 Lync Server 2013 內的內部和外部通訊</A>。



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>在網站層級設定封存選項

1.  從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server 2013 [控制台]。 如需可用於啟動 Lync Server 2013 [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。

4.  在 [**存檔**設定] 頁面上，按一下 [**新增**]，然後按一下 [**網站**設定]。

5.  在 [**選取網站**] 中，選取要設定為要存檔的網站。

6.  在 [**新增封存設定**] 的 [**存檔設定**] 下拉式清單方塊中，執行下列其中一項操作：
    
      - 若要只針對立即訊息（IM）會話啟用封存，請按一下 [封存**IM 會話**]。
    
      - 若要在 IM 會話與會議中啟用封存功能，請按一下 [封存**im 和網路會議會話**]。
    
      - 若要停用原則封存，請按一下 [**停**用封存]。

7.  此外，在 [新增封存]**設定**中，請執行下列動作：
    
      - 若要在封存無法使用時封鎖活動，請選取 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。
    
      - 若要使用 Microsoft Exchange Server 儲存存檔資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。
    
      - 若要啟用資料清除，請選取 [**啟用 [清除封存資料**] 核取方塊，然後執行下列其中一項操作：
        
          - 若要指定在特定天數後進行清除，請按一下 **[清除匯出的存檔資料]，並儲存在最長持續時間（天數）之後的儲存封存資料**，然後指定天數。
        
          - 若要限制清除以封存已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。

8.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

