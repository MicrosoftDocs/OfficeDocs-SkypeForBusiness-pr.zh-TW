---
title: Lync Server 2013：從評估版本更新
description: Lync Server 2013：從評估版本更新。
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
ms.openlocfilehash: 340badf9f5d2506c50cf8c03faa82223eabbd5af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546249"
---
# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="f39a2-103">從 Lync Server 2013 評估版更新</span><span class="sxs-lookup"><span data-stu-id="f39a2-103">Updating from the evaluation version of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f39a2-104">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="f39a2-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="f39a2-105">如果您已安裝 Microsoft Lync Server 2013 的評估版，最後必須更新該安裝軟體的授權副本;這是因為評估版本在安裝後會到期180天。</span><span class="sxs-lookup"><span data-stu-id="f39a2-105">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="f39a2-106">不過，您不需要完全解除安裝評估版本，然後再安裝授權版本。</span><span class="sxs-lookup"><span data-stu-id="f39a2-106">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="f39a2-107">在取得有效的授權金鑰之後，您可以在擔任 Lync Server 前端伺服器、Director 或 Edge Server 的每一部電腦上執行下列程式，以更新 Lync Server 2013 的評估版。</span><span class="sxs-lookup"><span data-stu-id="f39a2-107">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="f39a2-108">請注意，您不需要更新執行其他伺服器角色 (如監控伺服器或封存伺服器) 的電腦。</span><span class="sxs-lookup"><span data-stu-id="f39a2-108">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="f39a2-109">從 Microsoft Lync Server 2013 的評估版本更新</span><span class="sxs-lookup"><span data-stu-id="f39a2-109">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="f39a2-110">若要將電腦從 Lync Server 2013 評估版更新為軟體的授權版本：</span><span class="sxs-lookup"><span data-stu-id="f39a2-110">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="f39a2-111">**從 Microsoft Lync Server 2013 的評估版本更新**</span><span class="sxs-lookup"><span data-stu-id="f39a2-111">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="f39a2-112">以本機系統管理員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="f39a2-112">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="f39a2-113">依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="f39a2-113">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f39a2-114">在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="f39a2-114">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="f39a2-115">請注意，您可能需要指定檔案 server.msi 的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="f39a2-115">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="f39a2-116">您可以在 Lync Server 磁片區媒體安裝檔案的 Setup 資料夾中找到此檔案。</span><span class="sxs-lookup"><span data-stu-id="f39a2-116">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="f39a2-117">安裝程式完成執行之後，從命令提示字元中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="f39a2-117">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="f39a2-118">在執行 Lync Server 評估副本的任何其他前端伺服器、Director 或 Edge Server 上重複此程式。</span><span class="sxs-lookup"><span data-stu-id="f39a2-118">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="f39a2-119">您也應該在任何使用 Lync Server media 安裝檔案部署的分支 Office 伺服器上執行此程式。</span><span class="sxs-lookup"><span data-stu-id="f39a2-119">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="f39a2-120">如果您不確定 Lync Server 的評估版本是在指定的電腦上執行，您可以在 Lync Server 管理命令介面中執行下列命令，以驗證：</span><span class="sxs-lookup"><span data-stu-id="f39a2-120">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="f39a2-121">[Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) Cmdlet 會分析本機電腦，並回報下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="f39a2-121">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="f39a2-122">已在電腦上安裝 Lync Server 大量授權金鑰，這表示不需要更新。</span><span class="sxs-lookup"><span data-stu-id="f39a2-122">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="f39a2-123">已安裝 Lync Server 評估授權碼，這表示必須更新電腦。</span><span class="sxs-lookup"><span data-stu-id="f39a2-123">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="f39a2-p104">電腦上不需要大量授權金鑰。只有在前端伺服器、Director 及 Edge Server 上才需要從評估版本更新為授權版本。</span><span class="sxs-lookup"><span data-stu-id="f39a2-p104">That no volume license key is required on the computer. Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

