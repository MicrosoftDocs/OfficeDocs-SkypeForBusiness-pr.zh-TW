---
title: Lync Server 2013：設定使用者的封存原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58d7b149c55d8daac9cb47f5e3ab0e1b4ea0596
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509730"
---
# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a>在 Lync Server 2013 中設定使用者的封存原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

您可以為使用者建立和設定封存原則，然後將原則套用至特定的使用者或使用者群組，來啟用或停用特定使用者的封存。 使用者原則會覆寫任何全域原則或網站原則。 封存原則只有在您未使用 Microsoft Exchange 整合時才會套用，否則，如果您使用 Microsoft Exchange 整合，但有部分使用者未位於 Exchange 2013，且其信箱置於 In-Place 保留狀態，則僅適用。

如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱 [Lync Server 2013](lync-server-2013-how-archiving-works.md) 規劃檔、部署檔或作業檔中的封存運作方式。

<div>


> [!NOTE]  
> 如果您為部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 2013 上的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。 如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A> 封存的原則。<BR>您應該先在封存設定中指定所有適當的選項，才能在封存原則中封存內部或外部通訊。 如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A> 中設定封存選項。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定封存的使用者原則](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [使用 Exchange Server 整合時設定在 Lync Server 2013 中封存的原則](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

