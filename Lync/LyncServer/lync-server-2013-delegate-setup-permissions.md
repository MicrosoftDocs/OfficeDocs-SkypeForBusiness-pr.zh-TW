---
title: Lync Server 2013：委派設定權限
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
ms.openlocfilehash: 245fa0cb3bb5393f1d0f09a3f3b9c10176c015ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="79b58-102">在 Lync Server 2013 中委派設定權限</span><span class="sxs-lookup"><span data-stu-id="79b58-102">Delegate setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79b58-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="79b58-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="79b58-104">如果您不想將網域系統管理員群組的成員資格授與部署 Lync server 2013 的使用者或群組，您可以讓 RTCUniversalServerAdmins 群組的成員在執行 Lync server 2013 的伺服器上執行**enable-CsTopology** Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="79b58-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="79b58-105">根據預設，RTCUniversalServerAdmins 群組的成員不具備執行此 Cmdlet 的能力。</span><span class="sxs-lookup"><span data-stu-id="79b58-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="79b58-106">在執行 Lync Server 的伺服器上，您可以使用**授與 CsSetupPermission** Cmdlet，並指定執行 lync server 2013 之伺服器的電腦物件所在的組織單位（OU），授與管理員權利和許可權，以執行**CsTopology** 。</span><span class="sxs-lookup"><span data-stu-id="79b58-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="79b58-107">當您安裝 Lync Server 時所進行的網域準備不會自動新增許可權，讓 RTCUniversalServerAdmins 群組的成員可以執行 Enable CsTopology Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="79b58-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="79b58-108">也就是說，根據預設，您必須是網域管理員，才能啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="79b58-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="79b58-109">若要將 RTCUniversalServerAdmins 群組的成員賦予啟用拓撲的權利，您必須執行授與 CsSetupPermissions Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="79b58-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="79b58-110">此外，您將需要針對每個駐留執行 Lync Server 的電腦的 Active Directory 容器執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="79b58-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="79b58-111">請記住，這個 Cmdlet 只會授與 RTCUniversalServerAdmins 群組的許可權;無法使用 Cmdlet 來將許可權授與其他安全性群組或個別使用者。</span><span class="sxs-lookup"><span data-stu-id="79b58-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="79b58-112"><STRONG>Enable-CsTopology</STRONG>是可讓 RTCUniversalServerAdmins 群組成員設定和部署 Lync Server 2013 的重要 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="79b58-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="79b58-113">若要新增執行 Enable 的功能，請 CsTopology 至 [RTCUniversalServerAdmins] 群組</span><span class="sxs-lookup"><span data-stu-id="79b58-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="79b58-114">以委派使用者將在其上執行 CsTopology 的網域，以網域管理員群組的成員身分登**入**伺服器。</span><span class="sxs-lookup"><span data-stu-id="79b58-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="79b58-115">開啟 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="79b58-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="79b58-116">Lync Server 2013 管理命令介面會自動安裝在每個前端伺服器或已安裝 Lync Server 2013 系統管理工具的任何電腦上。</span><span class="sxs-lookup"><span data-stu-id="79b58-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="79b58-117">如需 Lync Server 2013 管理命令介面的詳細資訊，請參閱 Operations 檔中的[Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="79b58-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="79b58-118">從 Lync Server 2013 管理命令介面執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="79b58-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79b58-119">如果 OU 不在最上層，您必須提供完整的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="79b58-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="79b58-120">在下列範例中，OU 是「Lync Servers」，該伺服器位於 contoso.com 網域中。</span><span class="sxs-lookup"><span data-stu-id="79b58-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

