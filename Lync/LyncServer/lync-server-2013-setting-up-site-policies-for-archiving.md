---
title: Lync Server 2013：設定封存的網站原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c3845289399c005a7d4d67e07629f71e86b6184
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中設定封存的網站原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

您可以為每個網站建立及設定封存原則，以啟用或停用特定網站的封存。 網站原則會覆寫全域原則，但使用者原則會覆寫網站原則。 封存原則只有在您未使用 Microsoft Exchange 整合時才會套用，否則，如果您使用 Microsoft Exchange 整合，但有部分使用者未位於 Exchange 2013，且其信箱置於 In-Place 保留狀態，則僅適用。

如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱[Lync Server 2013](lync-server-2013-how-archiving-works.md)規劃檔、部署檔或作業檔中的封存運作方式。

<div>


> [!NOTE]  
> 如果您為部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 2013 上的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。 如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A>封存的原則。<BR>您應該先在封存設定中指定所有適當的選項，才能在封存原則中封存內部或外部通訊。 如需詳細資訊，請參閱部署檔中的在<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A>中設定封存選項。



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a>若要建立網站的封存原則

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 Lync Server 2013 控制台。

3.  在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。
    
    如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱[Lync Server 2013](lync-server-2013-how-archiving-works.md)規劃檔、部署檔或作業檔中的封存運作方式。

4.  按一下 [新增]****，然後按一下 [站台原則]****。

5.  在 [**選取網站**] 中，按一下要套用原則的網站。

6.  在 **[新增封存原則]** 中，執行下列動作：
    
      - 在 [**名稱**] 中，指定網站原則的名稱。
    
      - 在 [**描述**] 中，提供網站原則 (的相關資訊（例如，Redmond) 的網站原則）。
    
      - 若要控制指定網站的內部通訊封存，請選取或清除 [封存**內部通訊**] 核取方塊。
    
      - 若要控制指定網站的外部通訊封存，請選取或清除 [封存**外部通訊**] 核取方塊。

7.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

