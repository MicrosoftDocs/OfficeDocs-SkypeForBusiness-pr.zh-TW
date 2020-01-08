---
title: Lync Server 2013：設定及指派歸檔原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8b3b4f1f9465684d7c9139b8cd548caacf91c41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>在 Lync Server 2013 中設定及指派存檔原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

在 Lync Server 2013 中，您可以使用原則來針對託管于 Lync Server 2013 的使用者啟用和停用內部通訊與外部通訊的封存。 這包括下列歸檔原則：

  - 部署 Lync Server 2013 時預設建立的全域原則。

  - 您可以建立及使用的選擇性網站層級和使用者層級原則，以指定如何針對特定網站或使用者執行封存。

您最初是在部署封存時設定封存原則，但是您可以在部署之後變更、新增及刪除原則。 在 Lync Server 2013 的 [控制台] 中，您可以使用 [封存**與監控**] 群組的 [**存檔原則**] 頁面，來管理全域層級、網站層級及使用者層級的原則。

<div>


> [!NOTE]  
> 若要控制封存的實現，您必須指定歸檔設定中的選項，例如是否要封存 IM 或會議、使用重要模式，以及清除選項。 根據預設，全域存檔設定或任何網站或池封存設定中不會啟用任何選項。 您應該先在封存配置中指定所有適當的選項，才能在歸檔原則中啟用內部或外部通訊的封存。 如需詳細資訊，請參閱在作業檔中<A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">針對貴組織、網站和池管理 Lync Server 2013 中的 [封存配置選項</A>]。<BR>如果您將 Lync Server storage 與 Exchange 2013 儲存整合，Exchange 使用者原則的優先順序高於 Lync Server 2013 的歸檔原則，但只適用于駐留在 Exchange 2013 已將其信箱放在就地保留中的使用者。



</div>

如需如何執行原則的詳細資料，包括原則的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 存檔中的運作方式](lync-server-2013-how-archiving-works.md)]。 如需如何在部署之後管理原則的詳細資料，請參閱在作業檔中[管理 Lync Server 2013 內的內部和外部通訊](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)。

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中設定存檔的全域原則](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [在 Lync Server 2013 中設定用於存檔的網站原則](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [在 Lync Server 2013 中設定使用者的歸檔原則](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

