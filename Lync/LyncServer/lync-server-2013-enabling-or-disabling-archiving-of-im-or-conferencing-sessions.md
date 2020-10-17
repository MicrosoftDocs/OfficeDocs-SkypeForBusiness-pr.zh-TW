---
title: 啟用或停用封存 IM 或會議會話
description: 啟用或停用封存 IM 或會議會話。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9861024bbd4f4a1558287139a37559f782fcf008
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546529"
---
# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a>啟用或停用 Lync Server 2013 中的 IM 或會議會話的封存

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

在 [Lync Server 2013 控制台] 中，您可以使用封存設定來啟用及停用 IM、會議會話或兩者的封存。 這包含下列封存組態：

  - 當您部署 Lync Server 2013 時，預設會建立全域設定。

  - 選用的網站層級和集區層級組態，可建立及用於指定針對特定網站或集區如何實作封存。

您一開始部署封存時會設定封存組態，但是在部署後可以變更、新增及刪除組態。 如需如何執行封存設定的詳細資訊，包括您可以指定哪些選項以及封存設定的階層，請參閱規劃檔、部署檔或作業檔中的封存 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 。

<div>


> [!NOTE]
> 若要使用封存，您必須設定封存原則，以指定是否啟用內部通訊、外部通訊或同時適用于 Lync Server 2013 的使用者的封存。 依據預設，都不會啟用內部或外部通訊的封存。 在任何原則中啟用封存之前，您應該為您的部署指定適當的封存設定，以及針對特定網站和集區（選用）指定適當的封存設定，如本節所述。 如需啟用封存的詳細資訊，請參閱部署檔中的設定 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013</A> 中的封存原則。<BR>如果您在部署封存後決定要使用 Microsoft Exchange 整合將封存資料和檔案儲存在 Exchange 2013 伺服器上，而且所有使用者都位於 Exchange 2013 伺服器上，則應該從拓撲中移除 SQL Server 資料庫設定。 您必須使用拓撲產生器來執行這項作業。 如需詳細資訊，請參閱 Operations 檔中的 <A href="lync-server-2013-changing-archiving-database-options.md">變更 Lync Server 2013</A> 中的封存資料庫選項。



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a>啟用或停用封存 IM 或會議會話

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中 **，按一下 [****監視與**封存]，然後按一下 [封存設定]。

4.  從封存設定清單中選取適當的全域、網站或集區設定，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]，然後執行下列動作：
    
      - 若只要啟用立即訊息 (IM) 工作階段的封存，請按一下 **[封存 IM 工作階段]**。
    
      - 若要同時啟用 IM 會話和會議的封存，請按一下 [封存 **im 和會議會話**]。
    
      - 若要停用原則的封存，請按一下 **[停用封存]**。

5.  按一下 **[認可]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[為您的組織、網站及集區管理 Lync Server 2013 中的封存設定選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[在 Lync Server 2013 中設定和指派封存原則](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

