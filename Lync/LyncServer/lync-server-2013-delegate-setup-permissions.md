---
title: Lync Server 2013： 委派設定權限
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
ms.openlocfilehash: d5660a78bcad4d125fbf32204331b433978a831d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="76e06-102">Lync Server 2013 中的委派設定權限</span><span class="sxs-lookup"><span data-stu-id="76e06-102">Delegate setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76e06-103">_**上次修改主題：** 2014年-02-05_</span><span class="sxs-lookup"><span data-stu-id="76e06-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="76e06-104">如果您不想要授與使用者或群組，已部署 Lync Server 2013 中的 Domain Admins 群組的成員資格，您可以啟用要執行**Enable-cstopology**的 RTCUniversalServerAdmins 群組的成員 執行 Lync Server 2013 的伺服器上的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76e06-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="76e06-105">根據預設，以 RTCUniversalServerAdmins 群組的成員沒有執行此 cmdlet 的功能。</span><span class="sxs-lookup"><span data-stu-id="76e06-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="76e06-106">您系統管理員權限授與的權限執行 Lync Server 使用**Grant-cssetuppermission** cmdlet 並指定組織單位 (OU) 執行 Lync Server 2013 之伺服器的電腦物件的所在位置的伺服器上執行**Enable-cstopology** 。</span><span class="sxs-lookup"><span data-stu-id="76e06-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="76e06-107">當您安裝 Lync Server 的網域準備工作不會自動新增權限可讓執行 Enable-cstopology 指令程式，以 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="76e06-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="76e06-108">這代表根據預設，您必須為網域系統管理員才能啟用拓樸。</span><span class="sxs-lookup"><span data-stu-id="76e06-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="76e06-109">您必須執行 Grant-CsSetupPermissions Cmdlet，才能給予 RTCUniversalServerAdmins 群組成員權限以啟用拓樸。</span><span class="sxs-lookup"><span data-stu-id="76e06-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="76e06-110">此外，您必須針對每一個 Active Directory 容器中會存放在執行 Lync Server 的電腦執行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76e06-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="76e06-111">請記住，這個 Cmdlet 只會將權限授與 RTCUniversalServerAdmins 群組；您無法使用這個 Cmdlet 將權限授與其他安全性群組或個別使用者。</span><span class="sxs-lookup"><span data-stu-id="76e06-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76e06-112"><STRONG>Enable-cstopology</STRONG>是允許 RTCUniversalServerAdmins 群組成員設定及部署 Lync Server 2013 的主要 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76e06-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="76e06-113">若要新增至 RTCUniversalServerAdmins 群組執行 Enable-cstopology 的能力</span><span class="sxs-lookup"><span data-stu-id="76e06-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="76e06-114">委派的使用者將執行**Enable-cstopology**的網域之 Domain Admins 群組成員身分登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="76e06-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="76e06-115">開啟 [Lync Server 2013 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="76e06-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="76e06-116">Lync Server 2013 管理命令介面會自動安裝在每部前端伺服器或 Lync Server 2013 系統管理工具必須已安裝的任何電腦上。</span><span class="sxs-lookup"><span data-stu-id="76e06-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="76e06-117">如需 Lync Server 2013 管理命令介面的詳細資訊，請參閱作業文件中的[Lync Server 2013 管理命令介面](lync-server-2013-lync-server-management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="76e06-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="76e06-118">從 Lync Server 2013 管理命令介面中執行下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="76e06-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="76e06-119">如果 OU 不是最上層網站，您必須提供的完整網域名稱。</span><span class="sxs-lookup"><span data-stu-id="76e06-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="76e06-120">在下列範例中，OU 為"Lync Servers 」，也就是 contoso.com 網域中。</span><span class="sxs-lookup"><span data-stu-id="76e06-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

