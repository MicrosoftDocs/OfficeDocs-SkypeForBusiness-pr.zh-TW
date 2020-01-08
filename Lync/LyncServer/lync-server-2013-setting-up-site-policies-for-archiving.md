---
title: Lync Server 2013：設定用於存檔的網站原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08a4ccd7f88f21aaf0c7e3d1575b9e4a887c31d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中設定用於存檔的網站原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

您可以建立並設定每個網站的存檔原則，以啟用或停用特定網站的封存。 網站原則會覆寫全域原則，但使用者原則會覆寫網站原則。 如果您不使用 Microsoft Exchange 整合，或如果您使用的是 Microsoft Exchange 整合，但不是駐留在 Exchange 2013 的部分使用者，且其信箱放在就地保留中，則只適用存檔原則。

如需有關歸檔原則運作方式的詳細資料，包括全域、網站和使用者原則的階層，請參閱 Lync Server 2013 規劃檔、部署檔或作業檔[中的存檔運作方式](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 如果您針對您的部署啟用 Microsoft Exchange 整合，Exchange 就地保留原則會控制是否針對託管于 Exchange 2013 的使用者啟用封存，並將其信箱放在就地保留中。 如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</A>。<BR>您應該先在封存配置中指定所有適當的選項，才能在歸檔原則中封存內部或外部通訊。 如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A>中的 [設定封存選項]。



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a>建立網站的存檔原則

1.  從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server 2013 [控制台]。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。
    
    如需有關歸檔原則運作方式的詳細資料，包括全域、網站和使用者原則的階層，請參閱 Lync Server 2013 規劃檔、部署檔或作業檔[中的存檔運作方式](lync-server-2013-how-archiving-works.md)。

4.  按一下 [新增]****，然後按一下 [站台原則]****。

5.  在 [**選取網站**] 中，按一下要套用原則的網站。

6.  在**新**的 [封存原則] 中，執行下列動作：
    
      - 在 [**名稱**] 中，指定網站原則的名稱。
    
      - 在 [**描述**] 中，提供網站原則的相關資訊（例如，雷蒙德的網站原則）。
    
      - 若要控制指定網站內部通訊的歸檔，請選取或清除 [封存**內部通訊**] 核取方塊。
    
      - 若要控制指定網站外部通訊的存檔，請選取或清除 [封存**外部通訊**] 核取方塊。

7.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

