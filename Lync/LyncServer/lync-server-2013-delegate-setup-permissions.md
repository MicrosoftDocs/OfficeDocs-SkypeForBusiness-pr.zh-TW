---
title: Lync Server 2013：委派設定許可權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453da166895c79cafe9f9637163e93a63ebccd75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504280"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="98635-102">在 Lync Server 2013 中委派設定許可權</span><span class="sxs-lookup"><span data-stu-id="98635-102">Delegate setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98635-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="98635-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="98635-104">如果您不想要將 Domain Admins 群組的成員資格授與部署 Lync Server 2013 的使用者或群組，您可以啟用 RTCUniversalServerAdmins 群組的成員，以**Enable-CsTopology**   在執行 lync server 2013 的伺服器上執行 Enable-CsTopology Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98635-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="98635-105">根據預設，RTCUniversalServerAdmins 群組的成員不具備執行此 Cmdlet 的能力。</span><span class="sxs-lookup"><span data-stu-id="98635-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="98635-106">在執行 Lync Server 的伺服器上，使用**Grant-CsSetupPermission**指令程式，並指定組織單位 (OU) （位於執行 lync server 2013 之伺服器的電腦物件所在的位置），授與系統管理員的許可權，以執行**Enable-CsTopology** 。</span><span class="sxs-lookup"><span data-stu-id="98635-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="98635-107">安裝 Lync Server 時所進行的網域準備不會自動新增允許 RTCUniversalServerAdmins 群組成員執行 Enable-CsTopology Cmdlet 的許可權。</span><span class="sxs-lookup"><span data-stu-id="98635-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="98635-108">這代表根據預設，您必須為網域系統管理員才能啟用拓樸。</span><span class="sxs-lookup"><span data-stu-id="98635-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="98635-109">您必須執行 Grant-CsSetupPermissions Cmdlet，才能給予 RTCUniversalServerAdmins 群組成員權限以啟用拓樸。</span><span class="sxs-lookup"><span data-stu-id="98635-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="98635-110">此外，您需要針對駐留執行 Lync Server 之電腦的每個 Active Directory 容器執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98635-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="98635-111">請記住，這個 Cmdlet 只會將權限授與 RTCUniversalServerAdmins 群組；您無法使用這個 Cmdlet 將權限授與其他安全性群組或個別使用者。</span><span class="sxs-lookup"><span data-stu-id="98635-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98635-112"><STRONG>Enable-CsTopology</STRONG> 是允許 RTCUniversalServerAdmins 群組成員設定及部署 Lync Server 2013 的金鑰 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98635-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="98635-113">新增執行 Enable-CsTopology 至 RTCUniversalServerAdmins 群組的能力</span><span class="sxs-lookup"><span data-stu-id="98635-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="98635-114">以委派使用者將在其上執行之網域的 Domain Admins 群組成員身分登入伺服器 **Enable-CsTopology**。</span><span class="sxs-lookup"><span data-stu-id="98635-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="98635-115">開啟 [Lync Server 2013 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="98635-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="98635-116">Lync Server 2013 管理命令介面會自動安裝在每一部前端伺服器或已安裝 Lync Server 2013 系統管理工具的任何電腦上。</span><span class="sxs-lookup"><span data-stu-id="98635-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="98635-117">如需 Lync Server 2013 管理命令介面的詳細資訊，請參閱 Operations 檔中的 [Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md) 介面。</span><span class="sxs-lookup"><span data-stu-id="98635-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="98635-118">從 Lync Server 2013 管理命令介面執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="98635-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98635-119">如果 OU 不是最上層，您必須提供完整的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="98635-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="98635-120">在下列範例中，OU 為 "Lync Servers" （位於 contoso.com 網域中）。</span><span class="sxs-lookup"><span data-stu-id="98635-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

