---
title: 確認組態設定
description: 驗證設定設定。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7bb1135e95dafe51e906768fe0f4f0d57bf2d6c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573109"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="d678a-103">確認組態設定</span><span class="sxs-lookup"><span data-stu-id="d678a-103">Verify configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d678a-104">_**主題上次修改日期：** 2012-09-06_</span><span class="sxs-lookup"><span data-stu-id="d678a-104">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="d678a-105">您可以在中央管理存放區所在的內部電腦上執行 Lync Server 2013 **Get-CsManagementStoreReplicationStatus** Cmdlet，或是在任何已加入的網域上安裝 ( # A0) 之 lync Server 2013 核心元件的電腦上，驗證設定資訊的複寫。</span><span class="sxs-lookup"><span data-stu-id="d678a-105">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="d678a-106">初始結果可能會指出複寫的狀態為 "False"，而非 "True"。</span><span class="sxs-lookup"><span data-stu-id="d678a-106">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="d678a-107">若是如此，請執行 **Invoke-CsManagementStoreReplication** Cmdlet，等候複寫完成，然後再次執行 **Get-CsManagementStoreReplicationStatus**。</span><span class="sxs-lookup"><span data-stu-id="d678a-107">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

