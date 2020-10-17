---
title: Lync Server 2013：設定 Director
description: Lync Server 2013：設定 Director。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b917000dec6d30fdec2963ff1e464fbb9a70805
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554109"
---
# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="2e496-103">在 Lync Server 2013 中設定 Director</span><span class="sxs-lookup"><span data-stu-id="2e496-103">Setting up the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e496-104">_**主題上次修改日期：** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="2e496-104">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="2e496-105">如果您是透過部署 Edge Server 來啟用外部使用者的存取，則有一個選項是部署 Director。</span><span class="sxs-lookup"><span data-stu-id="2e496-105">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="2e496-106">Director 是執行 Microsoft Lync Server 2013 的伺服器，用來驗證使用者要求，但不會家用任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="2e496-106">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="2e496-107">現在這不是必要條件，但如果您擔心效能並想要協助簡化驗證要求，它會非常有用。</span><span class="sxs-lookup"><span data-stu-id="2e496-107">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="2e496-108">如果您認為這對您的組織來說很不錯，設定 Director 或 Director 集區的步驟，與設定 Enterprise Edition 前端集區或 Standard Edition server 類似。</span><span class="sxs-lookup"><span data-stu-id="2e496-108">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="2e496-109">在拓撲產生器中定義 Director (s) 之後，您必須執行本節中的步驟。</span><span class="sxs-lookup"><span data-stu-id="2e496-109">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2e496-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="2e496-110">In This Section</span></span>

  - [<span data-ttu-id="2e496-111">在 Lync Server 2013 中安裝本機設定存放區</span><span class="sxs-lookup"><span data-stu-id="2e496-111">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="2e496-112">在 Director 上安裝 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e496-112">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="2e496-113">在 Lync Server 2013 中設定 Director 的憑證</span><span class="sxs-lookup"><span data-stu-id="2e496-113">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="2e496-114">在 Lync Server 2013 中的 Director 上啟動服務</span><span class="sxs-lookup"><span data-stu-id="2e496-114">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="2e496-115">在 Lync Server 2013 中測試 Director</span><span class="sxs-lookup"><span data-stu-id="2e496-115">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="2e496-116">在 Lync Server 2013 中設定自動用戶端 Sign-In 以使用 Director</span><span class="sxs-lookup"><span data-stu-id="2e496-116">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

