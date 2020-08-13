---
title: Lync Server 2013：設定封存選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd70d2742e54da801f80b07f1a00b97e0d91a990
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>在 Lync Server 2013 中設定封存選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

在 [Lync Server 2013 控制台] 中，您可以使用封存設定來指定封存的實施方式。 這包含下列封存組態：

  - 當您部署 Lync Server 2013 時，預設會建立全域設定。

  - 選用的網站層級和集區層級組態，可建立及用於指定針對特定網站或集區如何實作封存。

您一開始部署封存時會設定封存組態，但是在部署後可以變更、新增及刪除組態。 在 [Lync Server 2013 控制台] 中，您可以**使用 [封存****與監控**] 群組的 [封存設定] 頁面，以管理全域層級、網站層級及集區層級的設定。 如需如何執行封存設定的詳細資訊，包括您可以指定哪些選項以及封存設定的階層，請參閱規劃檔、部署檔或作業檔中的封存[如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md)。 如需如何在部署後管理設定的詳細資訊，請參閱 Operations 檔中的[管理組織、網站及集區之 Lync Server 2013 中的封存配置選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)。

<div>


> [!NOTE]  
> 若要使用封存，您必須設定封存原則，以指定是否啟用內部通訊、外部通訊或同時適用于 Lync Server 2013 的使用者的封存。 依據預設，都不會啟用內部或外部通訊的封存。 在任何原則中啟用封存之前，您應該為您的部署指定適當的封存設定，以及針對特定網站和集區（選用）指定適當的封存設定，如本節所述。 如需啟用封存的詳細資訊，請參閱部署檔中的設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013</A>中的封存原則。<BR>如果您部署中的所有使用者未使用 Microsoft Exchange 整合，您必須設定封存原則，以指定是否要啟用內部通訊、外部通訊或兩者的封存。 根據預設，使用 Lync Server 2013 封存資料庫時，未啟用內部或外部通訊的封存資料的封存。 以任何原則啟用封存之前，您應先為部署指定適用的封存組態，然後如上一節中所述，選用地針對網站與集區指定封存組態。 如需啟用封存以用於 Lync Server 2013 封存資料庫的詳細資訊，請參閱部署檔中的設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync server 2013</A>中的封存原則。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定全域層級的封存選項](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [在 Lync Server 2013 中設定網站的封存選項](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [在 Lync Server 2013 中設定集區的封存選項](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

