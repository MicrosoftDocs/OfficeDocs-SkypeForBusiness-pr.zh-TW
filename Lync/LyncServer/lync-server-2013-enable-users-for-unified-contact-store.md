---
title: Lync Server 2013： 啟用整合連絡人存放區的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f4bd8e47259f7480f32e0fa6047657464a459de
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="dbb58-102">啟用使用者的 Lync Server 2013 中整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="dbb58-102">Enable users for unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbb58-103">_**主題上次修改日期：** 2012年-10-07_</span><span class="sxs-lookup"><span data-stu-id="dbb58-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="dbb58-104">當您部署 Lync Server 2013，並發行拓撲時，則整合連絡人存放區預設會啟用所有使用者。</span><span class="sxs-lookup"><span data-stu-id="dbb58-104">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="dbb58-105">您不需要採取任何其他的動作，來啟用整合連絡人存放區之後，您將部署 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="dbb58-105">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="dbb58-106">不過，您可以使用 **Set-CsUserServicesPolicy** Cmdlet 自訂哪些連絡人有整合連絡人存放區可用。</span><span class="sxs-lookup"><span data-stu-id="dbb58-106">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="dbb58-107">您可以全域、依網站、依承租人或依個人或個人群組啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="dbb58-107">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="dbb58-108">啟用整合連絡人存放區的使用者</span><span class="sxs-lookup"><span data-stu-id="dbb58-108">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="dbb58-109">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="dbb58-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="dbb58-110">執行下列任一項作業：</span><span class="sxs-lookup"><span data-stu-id="dbb58-110">Do any of the following:</span></span>
    
      - <span data-ttu-id="dbb58-111">若要啟用整合連絡人存放區全域所有 Lync Server 使用者，請在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="dbb58-111">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="dbb58-112">若要對特定網站的使用者啟用整合連絡人存放區，請在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="dbb58-112">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="dbb58-113">例如：</span><span class="sxs-lookup"><span data-stu-id="dbb58-113">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="dbb58-114">若要依承租人啟用整合連絡人存放區，請在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="dbb58-114">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="dbb58-115">例如：</span><span class="sxs-lookup"><span data-stu-id="dbb58-115">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="dbb58-116">若要對特定使用者啟用整合連絡人存放區，請在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="dbb58-116">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dbb58-117">您也可以使用使用者別名或 SIP URI，而不使用使用者顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="dbb58-117">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="dbb58-118">例如：</span><span class="sxs-lookup"><span data-stu-id="dbb58-118">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dbb58-p102">在上一個範例中，第一個命令建立名稱為「UCS 已啟用使用者」<EM></EM> 的新個別使用者原則，而且將 UcsAllowed 旗標設定為 True。第二個指令將該原則指派給顯示名稱為 Ken Myer 的使用者，這表示目前已針對 Ken Myer 啟用整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="dbb58-p102">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

