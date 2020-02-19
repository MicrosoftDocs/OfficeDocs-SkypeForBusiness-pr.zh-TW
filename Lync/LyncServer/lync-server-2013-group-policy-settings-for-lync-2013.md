---
title: Lync 2013 的 Lync Server 2013： 群組原則設定
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
ms.openlocfilehash: 8cae5fdb813f7f58889dd1305b117f0e07ff294e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="d6163-102">Lync 2013 的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="d6163-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6163-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="d6163-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d6163-104">在舊版的 Lync 及 Office Communicator，獨立的 Communicator.adm 系統管理範本是適用於設定用戶端的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="d6163-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="d6163-105">Lync 2013 的新系統管理範本檔案 （.admx 和.adml 檔案） 會包含以及 Office 群組原則系統管理範本。</span><span class="sxs-lookup"><span data-stu-id="d6163-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="d6163-106">Lync 2013.admx 和.adml 檔案的可用性可讓您下載範本，並集中管理所有 Office 程式及語言套件的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="d6163-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="d6163-107">如需詳細資訊，請參閱 「 Office 2013 Administrative Template files （ADMX，ADML） 」 中的 Office 2013 文件<https://go.microsoft.com/fwlink/p/?linkid=267516>。</span><span class="sxs-lookup"><span data-stu-id="d6163-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="d6163-108">用戶端啟動原則</span><span class="sxs-lookup"><span data-stu-id="d6163-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="d6163-109">有幾個用戶端啟動原則是您必須在使用者第一次登入伺服器之前設定的。</span><span class="sxs-lookup"><span data-stu-id="d6163-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="d6163-110">因為在用戶端登入並開始從伺服器接收頻內佈建設定之前，這些原則就已生效，所以您可以使用 [群組原則] 來設定它們。</span><span class="sxs-lookup"><span data-stu-id="d6163-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="d6163-111">如需詳細資訊，請參閱部署文件中的[Lync Server 2013 中的設定用戶端啟動載入原則](lync-server-2013-configuring-client-bootstrapping-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d6163-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

