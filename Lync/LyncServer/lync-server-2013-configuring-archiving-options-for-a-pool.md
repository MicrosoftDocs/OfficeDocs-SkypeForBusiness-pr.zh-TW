---
title: Lync Server 2013：設定文件庫的封存選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae5547320a9af0f11870ad0dc92ba03e40d8af4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a>在 Lync Server 2013 中設定文件庫的封存選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

您可以在每個池的存檔設定中建立和設定選項，以指定要套用到特定池的存檔選項。 池設定會覆寫全域配置和網站設定，但僅適用于在池設定中指定的池。

如需有關存檔設定的運作方式（包括全域、網站和池設定的階層），請參閱在規劃檔、部署檔或作業檔中的 [ [Lync Server 2013 存檔] 的運作方式](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 在啟用封存前，您應該先在封存配置中指定所有適當的選項。 如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A>中的 [設定封存選項]。



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a>在池層級設定封存選項

1.  從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server 2013 [控制台]。 如需可用於啟動 Lync Server 2013 [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。

4.  **在 [封存**設定] 頁面上，按一下 [**新增**]，然後按一下 [**池配置**]。

5.  在 [**選取服務**] 中，選取要設定為要存檔的池。

6.  在 [新增封存]**設定**的 [封存**設定**] 下拉式清單中，選取下列其中一個封存選項：
    
      - **停用封存**
    
      - **封存 IM 工作階段**
    
      - **封存 IM 與 Web 會議工作階段**

7.  此外，在 [**新增封存設定**] 頁面上，執行下列動作：
    
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

