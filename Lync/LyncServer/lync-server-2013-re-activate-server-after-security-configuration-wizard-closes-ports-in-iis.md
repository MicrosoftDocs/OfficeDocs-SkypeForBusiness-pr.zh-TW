---
title: 安全性設定向導在 IIS 中關閉埠後重新開機伺服器
description: 安全性設定向導在 IIS 中關閉埠之後重新開機伺服器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d824845a7f89c28087a7b5d180a6ed017cb47ade
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579049"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="37635-103">安全性設定向導在 IIS 中關閉埠後重新開機伺服器</span><span class="sxs-lookup"><span data-stu-id="37635-103">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37635-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="37635-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="37635-105">某些 Lync Server 2013 角色會在網際網路資訊服務（) 埠4443）上執行 Web 服務 (IIS。</span><span class="sxs-lookup"><span data-stu-id="37635-105">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="37635-106">執行 Lync Server 部署嚮導、Bootstrapper.exe 或使用 **Enable-CsComputer** Cmdlet 會在防火牆中建立例外狀況，並開啟埠。</span><span class="sxs-lookup"><span data-stu-id="37635-106">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="37635-107">如果您接著執行 Windows Server 2008 R2 安全性設定向導 (或其他強化腳本) ，將會封鎖埠4443，而且外部用戶端將無法連絡 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="37635-107">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="37635-108">若要重新開啟埠，您可以直接修改防火牆例外狀況，也可以重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="37635-108">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="37635-109">使用部署嚮導重新開機伺服器</span><span class="sxs-lookup"><span data-stu-id="37635-109">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="37635-110">在 [Lync Server 部署嚮導] 頁面上，按一下 [**步驟2：安裝或移除 Lync Server 元件**] 旁邊的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="37635-110">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="37635-111">在 **[安裝 Lync Server 元件]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="37635-111">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="37635-112">在 **[執行命令]** 頁面上，當工作狀態顯示為完成後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="37635-112">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="37635-113">您也可以使用 bootstrapper.exe 或 <STRONG>Enable-CsComputer</STRONG> ，以重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="37635-113">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

