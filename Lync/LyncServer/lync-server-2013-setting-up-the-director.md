---
title: Lync Server 2013：設定 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18de0fe7b06bbeed714aca444e75086fba9579e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="d8631-102">在 Lync Server 2013 中設定 Director</span><span class="sxs-lookup"><span data-stu-id="d8631-102">Setting up the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8631-103">_**主題上次修改日期：** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="d8631-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="d8631-104">如果您要透過部署邊緣伺服器來啟用外部使用者存取權，其中一個選項就是部署控制器。</span><span class="sxs-lookup"><span data-stu-id="d8631-104">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="d8631-105">控制器是執行 Microsoft Lync Server 2013 的伺服器，可驗證使用者要求，但不會家用任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d8631-105">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="d8631-106">現在這不是必要的做法，但如果您擔心效能並想要協助簡化驗證要求，這會很有説明。</span><span class="sxs-lookup"><span data-stu-id="d8631-106">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="d8631-107">如果您認為這對於您的組織而言是一個不錯的想法，設定主管或主管池的步驟與設定企業版前端池或標準版伺服器類似。</span><span class="sxs-lookup"><span data-stu-id="d8631-107">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="d8631-108">在拓撲建立器中定義主管之後，您必須執行本節中的步驟。</span><span class="sxs-lookup"><span data-stu-id="d8631-108">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d8631-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="d8631-109">In This Section</span></span>

  - [<span data-ttu-id="d8631-110">在 Lync Server 2013 中安裝本機設定存放區</span><span class="sxs-lookup"><span data-stu-id="d8631-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="d8631-111">在 Director 上安裝 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8631-111">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="d8631-112">在 Lync Server 2013 中設定 Director 的憑證</span><span class="sxs-lookup"><span data-stu-id="d8631-112">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="d8631-113">在 Lync Server 2013 中的 Director 上啟動服務</span><span class="sxs-lookup"><span data-stu-id="d8631-113">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="d8631-114">在 Lync Server 2013 中測試 Director</span><span class="sxs-lookup"><span data-stu-id="d8631-114">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="d8631-115">在 Lync Server 2013 中設定用戶端自動登入以使用 Director</span><span class="sxs-lookup"><span data-stu-id="d8631-115">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

