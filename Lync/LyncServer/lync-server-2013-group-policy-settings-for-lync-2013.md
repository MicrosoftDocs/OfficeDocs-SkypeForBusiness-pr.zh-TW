---
title: Lync Server 2013： Lync 2013 的群組原則設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e075af74fd081e49daad0768a33c9769e8a633bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="d2c01-102">Lync 2013 的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="d2c01-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2c01-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d2c01-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d2c01-104">在舊版 Lync 和 Office Communicator 中，有一個獨立的 Communicator 管理範本可供您設定用戶端群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="d2c01-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="d2c01-105">在 Lync 2013 中，新的系統管理範本檔案（admx 與 adml 檔案）隨附于 Office 群組原則管理範本。</span><span class="sxs-lookup"><span data-stu-id="d2c01-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="d2c01-106">Lync 2013 admx 與 adml 檔案的可用性可讓您下載範本，並集中管理所有 Office 程式及語言套件的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="d2c01-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="d2c01-107">如需詳細資訊，請參閱 Office 2013 檔中的「Office 2013 管理範本檔案（ADMX、ADML <http://go.microsoft.com/fwlink/p/?linkid=267516>）」。</span><span class="sxs-lookup"><span data-stu-id="d2c01-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="d2c01-108">用戶端引導原則</span><span class="sxs-lookup"><span data-stu-id="d2c01-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="d2c01-109">在使用者第一次登入伺服器之前，您應該先設定幾個用戶端引導原則。</span><span class="sxs-lookup"><span data-stu-id="d2c01-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="d2c01-110">因為這些原則會在用戶端登入並開始從伺服器接收帶外配設設定前生效，所以您可以使用群組原則來進行設定。</span><span class="sxs-lookup"><span data-stu-id="d2c01-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="d2c01-111">如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定用戶端引導原則](lync-server-2013-configuring-client-bootstrapping-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d2c01-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

