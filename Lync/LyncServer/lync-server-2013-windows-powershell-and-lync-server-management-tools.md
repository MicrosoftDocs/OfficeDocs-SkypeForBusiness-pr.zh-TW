---
title: Lync Server 2013： Windows PowerShell 和 Lync Server 管理工具
description: Lync Server 2013： Windows PowerShell 和 Lync Server 管理工具。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c8d63974ad05a041eb446182cbc7f9336044b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546039"
---
# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="6a5cf-103">Windows PowerShell 和 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="6a5cf-103">Windows PowerShell and Lync Server 2013 management tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a5cf-104">_**主題上次修改日期：** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="6a5cf-104">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="6a5cf-105">在 Microsoft Lync Server 2013 中，管理工具是使用 Windows PowerShell 來執行。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-105">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="6a5cf-106">Windows PowerShell 包含命令列環境、產品特有的命令，以及完整的指令碼語言。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-106">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="6a5cf-107">使用 Windows PowerShell 執行的 Lync Server 2013 工具組括下列各項：</span><span class="sxs-lookup"><span data-stu-id="6a5cf-107">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="6a5cf-108">**拓撲**產生器。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-108">**Topology Builder**.</span></span> <span data-ttu-id="6a5cf-109">您可以使用拓撲產生器來建立、調整和發行您規劃的拓撲，並在開始伺服器安裝之前驗證拓撲。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-109">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="6a5cf-110">當您在個別伺服器上安裝 Lync Server 2013 時，伺服器會在安裝程式中讀取已發佈的拓撲，而安裝程式會以拓撲中的導向方式來部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-110">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="6a5cf-111">設定完成後，設定資訊會自動複寫到所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-111">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="6a5cf-112">只有使用拓撲產生器，才能將元件新增至部署。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-112">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="6a5cf-113">**Lync Server 管理命令**介面。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-113">**Lync Server Management Shell**.</span></span> <span data-ttu-id="6a5cf-114">您可以使用 Lync Server 管理命令介面來進行部署的完整命令列管理。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-114">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="6a5cf-115">**Lync Server 控制台**。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-115">**Lync Server Control Panel**.</span></span> <span data-ttu-id="6a5cf-116">您可以使用 Microsoft Lync Server 2013 控制台使用者介面管理部署中的最常見工作。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-116">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="6a5cf-117">這些工具使用 Windows PowerShell Cmdlet 來管理您的部署，包含接近550產品特有的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-117">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="6a5cf-118">Lync Server 2013 中包含的安全性 Cmdlet 主要是用來管理驗證，以及使用者權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-118">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="6a5cf-119">有各種各樣的指令程式可用於管理驗證，包括憑證和個人識別碼 (PIN) 驗證的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-119">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="6a5cf-120">此外，一些 Cmdlet 可讓您使用新的 Role-Based 存取控制 (RBAC) 功能委派 Lync Server 2013 的管理控制。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-120">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="6a5cf-121">如需 Lync Server Cmdlet 的詳細資訊，請參閱 [Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-121">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="6a5cf-122">Windows PowerShell 的腳本安全性功能是專門設計來協助避免舊版技術（包括 Microsoft Visual Basic Script Edition (VBScript) ）的腳本相關安全性問題。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-122">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="6a5cf-123">Windows PowerShell 的安全性功能主要是用來建立使用者無法輕易或無意中執行腳本的環境。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-123">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="6a5cf-124">依預設，Windows PowerShell 的安全性功能都會啟用。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-124">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="6a5cf-125">您可以修改這些功能的狀態，以滿足您的腳本需求和各種安全性目標。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-125">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="6a5cf-126">這並不是說命令介面讓使用者無法執行腳本。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-126">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="6a5cf-127">相反地，命令介面會使使用者在執行腳本時不會有這麼大的難度。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-127">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="6a5cf-128">如需詳細資訊，請參閱 Windows PowerShell Script Security at [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145) 。</span><span class="sxs-lookup"><span data-stu-id="6a5cf-128">For details, see Windows PowerShell Script Security at [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

