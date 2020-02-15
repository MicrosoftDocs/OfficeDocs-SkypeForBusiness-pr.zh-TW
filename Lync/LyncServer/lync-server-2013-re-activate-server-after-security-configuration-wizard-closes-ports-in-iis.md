---
title: 安全性設定] 精靈關閉 IIS 中的連接埠之後會重新啟動伺服器
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
ms.openlocfilehash: 388a39c81af2f7e3ca4e0c61f468b283deaa7a4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="11778-102">安全性設定] 精靈關閉 IIS 中的連接埠之後會重新啟動伺服器</span><span class="sxs-lookup"><span data-stu-id="11778-102">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11778-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="11778-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="11778-104">某些 Lync Server 2013 角色執行網際網路資訊服務 (IIS) 連接埠 4443 上的 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="11778-104">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="11778-105">執行 Lync Server 部署精靈，Bootstrapper.exe，或使用**Enable-cscomputer**指令程式會建立例外狀況防火牆中並開啟連接埠。</span><span class="sxs-lookup"><span data-stu-id="11778-105">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="11778-106">如果您再執行 Windows Server 2008 R2 的安全性設定精靈 （或其他強化指令碼），將會封鎖連接埠 4443，與外部用戶端將無法連絡 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="11778-106">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="11778-107">若要重新開啟連接埠您可以直接修改防火牆例外狀況，或重新啟動伺服器。</span><span class="sxs-lookup"><span data-stu-id="11778-107">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="11778-108">使用 [部署精靈重新啟動伺服器</span><span class="sxs-lookup"><span data-stu-id="11778-108">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="11778-109">在 [Lync Server 部署精靈] 頁面上，按一下 [**執行**下一步] 為**步驟 2： 安裝或移除 Lync Server 元件**。</span><span class="sxs-lookup"><span data-stu-id="11778-109">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="11778-110">在 **[安裝 Lync Server 元件]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="11778-110">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="11778-111">在 **[執行命令]** 頁面上，當工作狀態顯示為完成後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="11778-111">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="11778-112">您也可以使用 bootstrapper.exe 或<STRONG>Enable-cscomputer</STRONG>重新啟動伺服器。</span><span class="sxs-lookup"><span data-stu-id="11778-112">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

