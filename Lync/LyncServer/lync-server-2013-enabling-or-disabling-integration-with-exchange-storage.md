---
title: Lync Server 2013：啟用或停用與 Exchange storage 的整合
description: Lync Server 2013：啟用或停用與 Exchange storage 的整合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42d140bd99bdc4aa86bea2f6ad310c4e06f06faf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546539"
---
# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a>啟用或停用與 Exchange storage 的 Lync Server 2013 整合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

在 [Lync Server 2013 控制台] 中，您可以使用封存設定來啟用及停用與 Exchange 儲存的整合。 這包含下列封存組態：

  - 當您部署 Lync Server 2013 時，預設會建立全域設定。

  - 選用的網站層級和集區層級組態，可建立及用於指定針對特定網站或集區如何實作封存。

如需如何執行封存設定的詳細資訊，包括您可以指定哪些選項以及封存設定的階層，請參閱規劃檔、部署檔或作業檔中的封存 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 。

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a>啟用或停用 Microsoft Exchange storage 的整合

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中 **，按一下 [****監視與**封存]，然後按一下 [封存設定]。

4.  按一下封存組態清單中適當的全域、網站或集區組態名稱，再依序按一下 [編輯]**** 和 [顯示詳細資料]****，然後執行下列作業：
    
      - 若要啟用與 Exchange 2013 儲存的整合，請選取 [ **Microsoft Exchange 整合** ] 核取方塊。
    
      - 若要停用 Exchange 2013 儲存的整合，請清除 [ **Microsoft Exchange 整合** ] 核取方塊。

5.  按一下 **[認可]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的封存運作方式](lync-server-2013-how-archiving-works.md)  


[為您的組織、網站及集區管理 Lync Server 2013 中的封存設定選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

