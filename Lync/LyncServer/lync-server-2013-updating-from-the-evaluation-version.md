---
title: Lync Server 2013： 從的評估版本更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 703362f34c367d301e7d47e1bdc65f16a497ce88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="ef109-102">從 Lync Server 2013 的評估版本更新</span><span class="sxs-lookup"><span data-stu-id="ef109-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef109-103">_**主題上次修改日期：** 2012年-06-20 個_</span><span class="sxs-lookup"><span data-stu-id="ef109-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="ef109-104">如果您已安裝 Microsoft Lync Server 2013 的評估版本，您最後需要更新，安裝正版軟體;這是因為的評估版本已安裝後的 180 天後到期。</span><span class="sxs-lookup"><span data-stu-id="ef109-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="ef109-105">不過，您不需要完全解除安裝評估版本，然後再安裝授權版本。</span><span class="sxs-lookup"><span data-stu-id="ef109-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="ef109-106">相反地，在您取得有效的授權金鑰之後，您可以藉由執行下列程序做為 Lync Server 前端伺服器、 Director 或 Edge Server 的每部電腦上更新 Lync Server 2013 評估版。</span><span class="sxs-lookup"><span data-stu-id="ef109-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="ef109-107">請注意，您不需要更新執行其他伺服器角色 (如監控伺服器或封存伺服器) 的電腦。</span><span class="sxs-lookup"><span data-stu-id="ef109-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="ef109-108">從 Microsoft Lync Server 2013 的評估版本更新</span><span class="sxs-lookup"><span data-stu-id="ef109-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="ef109-109">若要更新為授權版本軟體的 [從 Lync Server 2013 評估版的電腦：</span><span class="sxs-lookup"><span data-stu-id="ef109-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="ef109-110">**從 Microsoft Lync Server 2013 的評估版本更新**</span><span class="sxs-lookup"><span data-stu-id="ef109-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="ef109-111">以本機系統管理員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="ef109-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="ef109-112">按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="ef109-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ef109-113">在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="ef109-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="ef109-114">請注意，您可能需要指定檔案 server.msi 的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="ef109-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="ef109-115">此檔案可以在 Lync Server 磁碟區媒體安裝檔案的安裝資料夾中找到。</span><span class="sxs-lookup"><span data-stu-id="ef109-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="ef109-116">安裝程式完成執行之後，從命令提示字元中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="ef109-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="ef109-117">重複此程序在任何其他前端伺服器、 Director 或 Edge 伺服器執行 Lync Server 評估複本。</span><span class="sxs-lookup"><span data-stu-id="ef109-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="ef109-118">也應該使用 Lync Server 媒體安裝檔案已部署任何 Branch Office 伺服器上執行此程序。</span><span class="sxs-lookup"><span data-stu-id="ef109-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="ef109-119">如果您不確定給定電腦上執行 Lync Server 的評估版本您可以確認藉由執行從 Lync Server 管理命令介面中的下列命令：</span><span class="sxs-lookup"><span data-stu-id="ef109-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="ef109-120">[Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) Cmdlet 會分析本機電腦，並回報下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ef109-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="ef109-121">Lync Server 的大量授權金鑰，已安裝在電腦上，這表示沒有更新是必要的。</span><span class="sxs-lookup"><span data-stu-id="ef109-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="ef109-122">必須更新已表示電腦安裝 Lync Server 評估授權金鑰。</span><span class="sxs-lookup"><span data-stu-id="ef109-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="ef109-p104">電腦上不需要大量授權金鑰。只有在前端伺服器、Director 及 Edge Server 上才需要從評估版本更新為授權版本。</span><span class="sxs-lookup"><span data-stu-id="ef109-p104">That no volume license key is required on the computer. Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

