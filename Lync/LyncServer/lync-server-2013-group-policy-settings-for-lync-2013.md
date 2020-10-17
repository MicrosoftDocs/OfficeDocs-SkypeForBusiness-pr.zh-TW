---
title: Lync Server 2013： Lync 2013 的群組原則設定
description: Lync Server 2013： Lync 2013 的群組原則設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c6f2b26fc19653b0098ed4775df1f9c8146986c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564179"
---
# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="40189-103">Lync 2013 的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="40189-103">Group Policy settings for Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40189-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="40189-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="40189-105">在舊版的 Lync 和 Office Communicator 中，有一個獨立的 Communicator 系統管理範本可用於設定用戶端群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="40189-105">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="40189-106">對於 Lync 2013，新的系統管理範本檔案 ( admx 和 adml 檔案) 隨附于 Office 群組原則系統管理範本。</span><span class="sxs-lookup"><span data-stu-id="40189-106">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="40189-107">Lync 2013 admx 和 adml 檔案的可用性可讓您下載範本，以及集中管理所有 Office 程式和語言套件的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="40189-107">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="40189-108">如需詳細資訊，請參閱 Office 2013 檔中的「Office 2013 系統管理範本檔案 (ADMX，ADML) 」 <https://go.microsoft.com/fwlink/p/?linkid=267516> 。</span><span class="sxs-lookup"><span data-stu-id="40189-108">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="40189-109">用戶端啟動原則</span><span class="sxs-lookup"><span data-stu-id="40189-109">Client Bootstrapping Policies</span></span>

<span data-ttu-id="40189-110">有幾個用戶端啟動原則是您必須在使用者第一次登入伺服器之前設定的。</span><span class="sxs-lookup"><span data-stu-id="40189-110">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="40189-111">因為在用戶端登入並開始從伺服器接收頻內佈建設定之前，這些原則就已生效，所以您可以使用 [群組原則] 來設定它們。</span><span class="sxs-lookup"><span data-stu-id="40189-111">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="40189-112">如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定用戶端引導原則](lync-server-2013-configuring-client-bootstrapping-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="40189-112">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

