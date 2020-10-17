---
title: 管理內部與外部通訊的封存
description: 管理內部及外部通訊的封存。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 857e4772d93ead01c3914b2ee04b71bddb1feed4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564129"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>在 Lync Server 2013 中管理內部和外部通訊的封存

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

在 Lync Server 2013 中，您可以使用封存原則來啟用和停用內部通訊和外部通訊的封存。如果您不使用 Microsoft Exchange 整合，或擁有的使用者不是位於 Exchange 2013 上，且其信箱置於 In-Place 保留狀態，請使用封存原則。 這包括下列封存原則：

  - 當您部署 Lync Server 2013 時，預設會建立全域原則。

  - 您可以選擇性建立的網站層級和使用者層級原則，並用來指定如何針對特定的網站或使用者實作封存。

您最初可以在部署封存時設定封存，但可在部署之後變更、新增及刪除原則。 在 [Lync Server 2013 控制台] 中，您可以使用 [封存**與監控**] 群組的 [封存**原則**] 頁面，以管理全域層級、網站層級和使用者層級的原則。 [！注意] 如果您將 Lync Server storage 與 Exchange 2013 儲存整合在一起，Exchange 使用者原則會優先于 Lync Server 2013 封存原則。

如需如何實施原則的詳細資訊，包括原則的階層，請參閱規劃檔、部署檔或作業檔中的封存 [在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md) 。

<div>


> [!NOTE]
> 若要控制封存的實作，您必須在封存設定中指定選項，例如，是否要封存 IM 或會議、使用關鍵模式及清除選項。 依預設，不會在全域封存設定或是任何網站或集區封存設定中啟用任何選項。 您應該先在封存設定中指定所有適當的選項，然後才能在封存原則中啟用對內部或外部通訊的封存。 如需詳細資訊，請參閱 Operations 檔中的 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">管理組織、網站及集區的 Lync Server 2013 中的封存配置選項</A> 。<BR>如果您為部署啟用 Microsoft Exchange 整合，Exchange 原則會控制是否為位於 Exchange 2013 上的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。 如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A> 封存的原則。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中建立封存原則，以針對特定網站或使用者啟用或停用內部或外部通訊的封存](lync-server-2013-create-archiving-policy-sites-users.md)

  - [變更 Lync Server 2013 中的封存原則，以啟用或停用組織、網站或使用者的內部或外部通訊的封存](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [將封存原則套用至 Lync Server 2013 中的使用者](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [使用 Exchange Server 整合時設定在 Lync Server 2013 中封存的原則](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [在 Lync Server 2013 中刪除封存原則](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

