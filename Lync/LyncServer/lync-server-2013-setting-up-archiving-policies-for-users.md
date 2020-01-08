---
title: Lync Server 2013：為使用者設定歸檔原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55a56ff5c44d10d112762bb06662e9266dbc270b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a>在 Lync Server 2013 中設定使用者的歸檔原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

您可以為使用者建立及設定存檔原則，然後將原則套用到特定的使用者或使用者群組，以啟用或停用特定使用者的封存。 使用者原則會覆寫任何全域原則或網站原則。 如果您不使用 Microsoft Exchange 整合，或如果您使用的是 Microsoft Exchange 整合，但不是駐留在 Exchange 2013 的部分使用者，且其信箱放在就地保留中，則只適用存檔原則。

如需有關歸檔原則運作方式的詳細資料，包括全域、網站和使用者原則的階層，請參閱 Lync Server 2013 規劃檔、部署檔或作業檔[中的存檔運作方式](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 如果您針對您的部署啟用 Microsoft Exchange 整合，Exchange 就地保留原則會控制是否針對託管于 Exchange 2013 的使用者啟用封存，並將其信箱放在就地保留中。 如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</A>。<BR>您應該先在封存配置中指定所有適當的選項，才能在歸檔原則中封存內部或外部通訊。 如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A>中的 [設定封存選項]。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中設定存檔的使用者原則](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

