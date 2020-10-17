---
title: Lync Server 2013：設定封存的全域原則
description: Lync Server 2013：設定封存的全域原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8f8125f458c4269626e0b1c929f2acb1a8de0b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556859"
---
# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中設定封存的全域原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

當您部署前端伺服器時，Lync Server 會建立通用的封存原則。 預設會在全域原則中停用封存。 「全域」原則會控制是否對整個部署啟用內部和外部通訊的封存，除非您設定網站或使用者原則，以覆寫全域原則，或您針對部分或所有使用者使用 Microsoft Exchange 整合。 如果您使用 Microsoft Exchange 整合，全域原則不會套用到所有位於 Exchange 2013 上的使用者，而且會將信箱置於 In-Place 保留狀態。

如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱 [Lync Server 2013](lync-server-2013-how-archiving-works.md) 規劃檔、部署檔或作業檔中的封存運作方式。

<div>


> [!NOTE]  
> 如果您為部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 2013 上的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。 如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A> 封存的原則。<BR>啟用封存前，應在封存組態中指定所有適當的選項。 如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A> 中設定封存選項。



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>使用 Lync Server 封存資料庫時設定封存的全域原則

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 Lync Server 2013 控制台。 如需可用於啟動 Lync Server 2013 控制台之不同方法的詳細資訊，請參閱 [Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。

4.  在 **[封存原則]** 頁面上，依序按一下 **[通用]** 和 **[編輯]**，然後按一下 **[顯示詳細資料]**。

5.  在 [編輯封存原則 - 通用]**** 中，執行下列動作：
    
      - 如果您不想要使用此預設全域名稱，請在 **[名稱]** 中指定全域原則的新名稱。
    
      - 在 **[描述]** 中，提供有關使用者原則的資訊 (例如，*divisionName* 的全域原則)。
    
      - 若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的內部通訊封存，請選取或清除 **[封存內部通訊]** 核取方塊。
    
      - 若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的外部通訊封存，請選取或清除 [封存外部通訊]**** 核取方塊。

6.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

