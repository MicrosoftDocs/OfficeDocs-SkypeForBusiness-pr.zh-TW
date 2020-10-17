---
title: Lync Server 2013：在 Lync Server 中設定封存的使用者原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee2074aa9608dad4adcfe85845e7b2e045276f59
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497510"
---
# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中設定封存的使用者原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

啟用或停用駐留在 Lync Server 2013 之特定使用者的封存，需要建立及設定一或多個使用者原則，然後將適當的原則套用至特定使用者或使用者群組。 使用者原則會覆寫網站和全域原則，但僅限於位於 Lync Server 2013 的使用者。

使用者永遠都是在 Lync Server 中託管。 如果啟用 Microsoft Exchange 整合，其信箱在 Microsoft Exchange Server 2013 中的使用者不需要在 Lync Server 中管理其封存原則。 這些具有封存的使用者將由 Exchange In-Place 保留進行管理。

如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱規劃檔、部署檔或作業檔中的封存 [在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md) 。

<div>


> [!NOTE]  
> 如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 2013 上的使用者啟用封存功能。 若要針對這些使用者啟用封存，則其信箱必須為就地保留狀態。 如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A> 封存的原則。<BR>啟用封存前，應在封存組態中指定所有適當的選項。 如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A> 中設定封存選項。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中建立及設定封存的使用者原則](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [將 Lync Server 封存原則套用至 Lync Server 2013 中的使用者](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

