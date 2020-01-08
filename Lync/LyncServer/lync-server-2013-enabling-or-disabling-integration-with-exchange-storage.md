---
title: Lync Server 2013：啟用或停用 Exchange 儲存體整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d2ded7e4cf586faf1f15ea6205aa23802413dc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a>啟用或停用 Lync Server 2013 與 Exchange 儲存空間的整合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

在 Lync Server 2013 [控制台] 中，您可以使用封存配置來啟用和停用 Exchange 儲存。 這包括下列歸檔設定：

  - 當您部署 Lync Server 2013 時預設會建立的全域配置。

  - 您可以建立及用來指定如何針對特定網站或池實施封存的選擇性網站層級和池層級設定。

如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 中的存檔運作方式](lync-server-2013-how-archiving-works.md)]。

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a>啟用或停用 Microsoft Exchange 儲存空間的整合

1.  從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。

4.  在歸檔設定清單中，按一下適當的全域、網站或池設定的名稱，按一下 [**編輯**]，按一下 [**顯示詳細資料**]，然後執行下列動作：
    
      - 若要啟用與 Exchange 2013 儲存空間的整合，請選取 [ **Microsoft Exchange 整合**] 核取方塊。
    
      - 若要停用 Exchange 2013 儲存區的整合，請清除 [ **Microsoft Exchange 整合**] 核取方塊。

5.  按一下 [認可]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[存檔在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md)  


[管理您組織、網站和池的 Lync Server 2013 中的封存配置選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

