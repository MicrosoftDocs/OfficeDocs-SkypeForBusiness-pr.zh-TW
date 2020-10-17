---
title: Lync Server 2013： Audio/Video (A/V) Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a83aa6c21be0a1055be091ab7195f3c03c4c6e2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508270"
---
# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="27b9e-102">在 Lync Server 2013 中 Audio/Video (A/V) Edge Server</span><span class="sxs-lookup"><span data-stu-id="27b9e-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27b9e-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="27b9e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="27b9e-104">A/V Edge 服務可讓內部使用者 (即已登入您組織網路的使用者) 將音訊和視訊共用給外部使用者 (即未登入您組織網路的使用者)。</span><span class="sxs-lookup"><span data-stu-id="27b9e-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="27b9e-105">除了音訊和影片之外，A/V Edge service 也會提供對此類內容的支援，以進行桌面共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="27b9e-105">In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="27b9e-106">A/V Edge service 主要使用 A/V Edge 設定進行管理;這些設定可讓您管理每個埠或每位使用者所要分配的最大頻寬量，並指定在必須更新權杖之前，可使用的驗證權杖的時間長度。</span><span class="sxs-lookup"><span data-stu-id="27b9e-106">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed.</span></span> <span data-ttu-id="27b9e-107">A/V Edge 設定設定可以套用到網站或個別 A/V Edge server。</span><span class="sxs-lookup"><span data-stu-id="27b9e-107">A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers.</span></span> <span data-ttu-id="27b9e-108">決定哪個設定集合優先時，請使用下列指南：</span><span class="sxs-lookup"><span data-stu-id="27b9e-108">When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="27b9e-109">服務範圍 (亦即在個別伺服器) 中的設定優先使用。</span><span class="sxs-lookup"><span data-stu-id="27b9e-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="27b9e-110">在網站範圍設定的設定優先于在全域範圍設定的設定。</span><span class="sxs-lookup"><span data-stu-id="27b9e-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="27b9e-111">不過，服務範圍設定也會取代網站範圍設定。</span><span class="sxs-lookup"><span data-stu-id="27b9e-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="27b9e-112">若個別伺服器裡未進行任何服務設定，且該伺服器所處的網站無任何網站設定，才會使用全域範圍的設定。</span><span class="sxs-lookup"><span data-stu-id="27b9e-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="27b9e-113">您只能使用 Lync Server PowerShell 和 CsAVEdgeConfiguration Cmdlet 來管理 A/V Edge service。</span><span class="sxs-lookup"><span data-stu-id="27b9e-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="27b9e-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="27b9e-114">In This Section</span></span>

  - [<span data-ttu-id="27b9e-115">傳回 Lync Server 2013 中 A/V Edge Server 設定資訊</span><span class="sxs-lookup"><span data-stu-id="27b9e-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="27b9e-116">在 Lync Server 2013 中建立或修改 A/V Edge Server 設定的集合</span><span class="sxs-lookup"><span data-stu-id="27b9e-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="27b9e-117">在 Lync Server 2013 中刪除現有的 A/V Edge Server 設定集合集合</span><span class="sxs-lookup"><span data-stu-id="27b9e-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

