---
title: Lync Server 2013：設定存檔選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98356b53940c6189abac5a4b554769093f84dd2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>在 Lync Server 2013 中設定封存選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

在 Lync Server 2013 的 [控制台] 中，您可以使用 [封存設定] 來指定歸檔的實施方式。 這包括下列歸檔設定：

  - 當您部署 Lync Server 2013 時預設會建立的全域配置。

  - 您可以建立及用來指定如何針對特定網站或池實施封存的選擇性網站層級和池層級設定。

您最初是在部署封存時設定封存配置，但您可以在部署之後變更、新增及刪除配置。 在 Lync Server 2013**的 [控制台**] 中，您可以使用 [封存**與監控**] 群組的 [封存設定] 頁面，來管理全域層級、網站層級和池層級的設定。 如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 中的存檔運作方式](lync-server-2013-how-archiving-works.md)]。 如需有關如何在部署之後管理設定的詳細資訊，請參閱在作業檔中[針對貴組織、網站和池管理 Lync Server 2013 中的 [封存配置選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)]。

<div>


> [!NOTE]  
> 若要使用封存，您必須設定封存原則，以指定是否要針對內部通訊啟用封存，或針對駐留在 Lync Server 2013 的使用者。 根據預設，不會針對內部或外部通訊啟用封存。 在任何原則中啟用封存前，您應該為您的部署指定適當的歸檔設定，也可以針對特定的網站和池指定適當的存檔配置，如本節所述。 如需啟用封存的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013 中的存檔原則</A>。<BR>如果您不是針對您部署中的所有使用者使用 Microsoft Exchange 整合，您必須設定存檔原則，以指定是否要針對內部通訊（針對外部通訊），或兩者啟用封存。 根據預設，在使用 Lync Server 2013 封存資料庫時，不會針對內部或外部通訊啟用封存來存檔資料。 在任何原則中啟用封存前，您應該為您的部署指定適當的歸檔設定，也可以針對特定的網站和池指定適當的存檔配置，如本節所述。 如需啟用封存以搭配 Lync Server 2013 存檔資料庫的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync server 2013 中的存檔原則</A>。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 的全域層級設定封存選項](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [在 Lync Server 2013 中設定網站的存檔選項](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [在 Lync Server 2013 中設定文件庫的封存選項](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

