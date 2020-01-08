---
title: Lync Server 2013：從評估版本更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b00fed276229cbaf0e960e28e622e490fb0bfbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="b3796-102">從 Lync Server 2013 評估版更新</span><span class="sxs-lookup"><span data-stu-id="b3796-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3796-103">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="b3796-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="b3796-104">如果您已安裝 Microsoft Lync Server 2013 評估版，最終必須更新該安裝軟體的授權複本;這是因為評估版本在安裝後會過期180天。</span><span class="sxs-lookup"><span data-stu-id="b3796-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="b3796-105">不過，您不需要完全卸載評估版本，然後再安裝授權版本。</span><span class="sxs-lookup"><span data-stu-id="b3796-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="b3796-106">在取得有效的授權金鑰之後，您可以在充當 Lync Server 前端伺服器、控制器或邊緣伺服器的每個電腦上執行下列程式，以更新 Lync Server 2013 的評估版本。</span><span class="sxs-lookup"><span data-stu-id="b3796-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="b3796-107">請注意，您不需要更新執行其他伺服器角色（例如監視伺服器或存檔伺服器）的電腦。</span><span class="sxs-lookup"><span data-stu-id="b3796-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="b3796-108">從評估版的 Microsoft Lync Server 2013 更新</span><span class="sxs-lookup"><span data-stu-id="b3796-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="b3796-109">若要將電腦從 Lync Server 2013 評估版更新為軟體的授權版本：</span><span class="sxs-lookup"><span data-stu-id="b3796-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="b3796-110">**從評估版的 Microsoft Lync Server 2013 更新**</span><span class="sxs-lookup"><span data-stu-id="b3796-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="b3796-111">以本機系統管理員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="b3796-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="b3796-112">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b3796-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b3796-113">在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="b3796-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="b3796-114">請注意，您可能需要指定檔案伺服器 .msi 的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="b3796-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="b3796-115">您可以在 Lync Server Volume 媒體安裝檔案的 [設定] 資料夾中找到此檔案。</span><span class="sxs-lookup"><span data-stu-id="b3796-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="b3796-116">安裝程式完成後，請從命令提示字元輸入以下內容，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="b3796-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="b3796-117">在執行 Lync Server 評估複本的任何其他前端伺服器、控制器或邊緣伺服器上，重複此程式。</span><span class="sxs-lookup"><span data-stu-id="b3796-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="b3796-118">您也應該在任何使用 Lync Server 媒體安裝檔案部署的分支機搆伺服器上執行此程式。</span><span class="sxs-lookup"><span data-stu-id="b3796-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="b3796-119">如果您不確定 Lync Server 的評估版本是否在指定的電腦上執行，您可以從 Lync Server Management Shell 中執行下列命令，以驗證：</span><span class="sxs-lookup"><span data-stu-id="b3796-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="b3796-120">[CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) Cmdlet 會分析本機電腦，並傳回下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b3796-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="b3796-121">Lync Server 大量授權金鑰已安裝在電腦上，這表示不需要更新。</span><span class="sxs-lookup"><span data-stu-id="b3796-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="b3796-122">已安裝 Lync Server 評估版授權金鑰，這表示電腦必須更新。</span><span class="sxs-lookup"><span data-stu-id="b3796-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="b3796-123">電腦上不需要大量的授權金鑰。</span><span class="sxs-lookup"><span data-stu-id="b3796-123">That no volume license key is required on the computer.</span></span> <span data-ttu-id="b3796-124">只有在前端伺服器、控制器和 Edge 伺服器上才需要從評估版更新為授權版本。</span><span class="sxs-lookup"><span data-stu-id="b3796-124">Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

