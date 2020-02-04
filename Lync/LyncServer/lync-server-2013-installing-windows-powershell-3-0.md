---
title: Lync Server 2013：安裝 Windows PowerShell 3.0
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cd8b4b48f2ff5a50ef7cafc1ec39671f672670f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a><span data-ttu-id="268f1-102">針對 Lync Server 2013 安裝 Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="268f1-102">Installing Windows PowerShell 3.0 for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="268f1-103">_**主題上次修改日期：** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="268f1-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="268f1-104">若要成功部署 Lync Server 2013，您需要在您的 Lync Server 拓撲中的每一部電腦上都要有 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="268f1-104">To deploy Lync Server 2013 successfully, you’ll need Windows PowerShell 3.0 on each computer that’s part of your Lync Server topology.</span></span>

<span data-ttu-id="268f1-105">現在，對於執行 Windows Server 2012 或 Windows Server 2012 R2 的系統，您不需要執行任何動作，而且可以繼續進行部署的下一個階段，因為這些作業系統隨附 PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="268f1-105">Now, for systems running Windows Server 2012 or Windows Server 2012 R2, you don’t need to do anything here, and can go ahead to the next stage of deployment, because PowerShell 3.0 is included with those operating systems.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="268f1-106">但對於執行 Windows Server 2008 R2 SP1 的系統，您必須先安裝 PowerShell 3.0，才能安裝 Lync Server 2013，否則無法運作。</span><span class="sxs-lookup"><span data-stu-id="268f1-106">But for systems running Windows Server 2008 R2 SP1, you’ll need to install PowerShell 3.0 as a prerequisite before you install Lync Server 2013, or things won’t work.</span></span> <span data-ttu-id="268f1-107">若要安裝 PowerShell 3.0，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>。</span><span class="sxs-lookup"><span data-stu-id="268f1-107">To install PowerShell 3.0, see <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>.</span></span> <span data-ttu-id="268f1-108">這是 PowerShell 3.0 下載頁面的直接連結，以及成功安裝的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="268f1-108">This is a direct link to the PowerShell 3.0 download page, along with information relating to installing it successfully.</span></span>



</div>

<span data-ttu-id="268f1-109">完成安裝之後，或者只要想要在繼續 Lync Server 部署之前檢查並確定，確認 PowerShell 3.0 在伺服器上是相當簡單的做法：</span><span class="sxs-lookup"><span data-stu-id="268f1-109">Once you’ve done the install, or if you just want to check and be sure before continuing with the Lync Server deployment, confirming that PowerShell 3.0 is on a server is pretty straightforward if you do this:</span></span>

1.  <span data-ttu-id="268f1-110">在您想要檢查的伺服器上，選擇 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，按一下 [ **Windows PowerShell**]，然後按一下 [ **windows powershell**]。</span><span class="sxs-lookup"><span data-stu-id="268f1-110">On the server you want to check, choose **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="268f1-111">在 Windows PowerShell 主控台中，在命令提示字元中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="268f1-111">In the Windows PowerShell console, type the following command at the command prompt, and then press ENTER:</span></span>
    
        Get-Host | Select-Object Version

3.  <span data-ttu-id="268f1-112">如果已安裝 Windows PowerShell 3.0，您會看到如下所示的輸出：</span><span class="sxs-lookup"><span data-stu-id="268f1-112">If Windows PowerShell 3.0 is installed you’ll see output that looks like this:</span></span>
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

