---
title: Lync Server 2013：在 Lync Server 中設定存檔的使用者原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3921956949f38390277328495398970203993377
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中設定存檔的使用者原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

針對駐留在 Lync Server 2013 的特定使用者啟用或停用封存需要建立及設定一或多個使用者原則，然後將適當的原則套用至特定的使用者或使用者群組。 使用者原則會覆寫網站和全域原則，但只適用于駐留在 Lync Server 2013 的使用者。

使用者永遠都是在 Lync Server 中託管。 如果已啟用 Microsoft Exchange 整合，則信箱是 Microsoft Exchange Server 2013 的使用者，不需要在 Lync Server 管理中擁有其存檔原則。 這些擁有存檔的使用者將由 Exchange 就地保留進行管理。

如需有關歸檔原則運作方式的詳細資料，包括全域、網站和使用者原則的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 存檔中的運作方式](lync-server-2013-how-archiving-works.md)]。

<div>


> [!NOTE]  
> 如果您已針對您的部署啟用 Microsoft Exchange 整合，請按 Exchange 就地保留原則控制是否已針對託管于 Exchange 2013 的使用者啟用封存。 針對這些使用者的存檔要求他們將其信箱放在就地保留中。 如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</A>。<BR>在啟用封存前，您應該先在封存配置中指定所有適當的選項。 如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A>中的 [設定封存選項]。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中建立及設定用於存檔的使用者原則](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [在 Lync Server 2013 中將 Lync Server 存檔原則套用至使用者](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

