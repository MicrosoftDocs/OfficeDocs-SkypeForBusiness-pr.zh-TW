---
title: 管理內部與外部通訊的存檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 891318ba677891916af678b74365026d20d69016
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>在 Lync Server 2013 中管理內部和外部通訊的存檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

在 Lync Server 2013 中，如果您不使用 Microsoft Exchange 整合，或者您的使用者未駐留在 Exchange 2013 上，且其信箱放在外，您可以使用封存原則來啟用和停用內部通訊與外部通訊的封存就地保留。 這包括下列歸檔原則：

  - 部署 Lync Server 2013 時預設建立的全域原則。

  - 您可以建立及使用的選擇性網站層級和使用者層級原則，以指定如何針對特定網站或使用者執行封存。

您最初是在部署封存時設定封存原則，但是您可以在部署之後變更、新增及刪除原則。 在 Lync Server 2013 的 [控制台] 中，您可以使用 [封存**與監控**] 群組的 [**存檔原則**] 頁面，來管理全域層級、網站層級及使用者層級的原則。 如果您將 Lync Server storage 與 Exchange 2013 儲存整合，Exchange 使用者原則就會優先于 Lync Server 2013 封存原則。

如需如何執行原則的詳細資料，包括原則的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 存檔中的運作方式](lync-server-2013-how-archiving-works.md)]。

<div>


> [!NOTE]
> 若要控制封存的實現，您必須指定歸檔設定中的選項，例如是否要封存 IM 或會議、使用重要模式，以及清除選項。 根據預設，全域存檔設定或任何網站或池封存設定中不會啟用任何選項。 您應該先在封存配置中指定所有適當的選項，才能在歸檔原則中啟用內部或外部通訊的封存。 如需詳細資訊，請參閱在作業檔中<A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">針對貴組織、網站和池管理 Lync Server 2013 中的 [封存配置選項</A>]。<BR>如果您針對您的部署啟用 Microsoft Exchange 整合，Exchange 原則會控制是否針對託管于 Exchange 2013 的使用者啟用封存，並將其信箱放在就地保留中。 如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</A>。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中建立存檔原則，以啟用或停用特定網站或使用者的內部或外部通訊的存檔](lync-server-2013-create-archiving-policy-sites-users.md)

  - [在 Lync Server 2013 中變更存檔原則，以啟用或停用貴組織、網站或使用者的內部或外部通訊的封存功能](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [將存檔原則套用至 Lync Server 2013 中的使用者](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [刪除 Lync Server 2013 中的存檔原則](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

