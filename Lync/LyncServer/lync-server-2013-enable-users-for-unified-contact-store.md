---
title: Lync Server 2013：為使用者啟用整合連絡人存放區
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
ms.openlocfilehash: 3df3cbd4d71a1decc3607263f2e98b159dc29b2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="44c46-102">在 Lync Server 2013 中為使用者啟用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="44c46-102">Enable users for unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44c46-103">_**主題上次修改日期：** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="44c46-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="44c46-104">當您部署 Lync Server 2013 併發布拓撲時，預設會為所有使用者啟用「整合連絡人存放區」。</span><span class="sxs-lookup"><span data-stu-id="44c46-104">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="44c46-105">您在部署 Lync Server 2013 之後，不需要採取任何其他動作即可啟用 [整合連絡人存放區]。</span><span class="sxs-lookup"><span data-stu-id="44c46-105">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="44c46-106">不過，您可以使用**CsUserServicesPolicy** Cmdlet 來自訂哪些使用者可以使用 [整合的連絡人] 存放區。</span><span class="sxs-lookup"><span data-stu-id="44c46-106">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="44c46-107">您可以在全球、由網站、由租使用者，或由個人或個人群組來啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="44c46-107">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="44c46-108">若要讓使用者使用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="44c46-108">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="44c46-109">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="44c46-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="44c46-110">請執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="44c46-110">Do any of the following:</span></span>
    
      - <span data-ttu-id="44c46-111">若要讓所有 Lync Server 使用者全域都能使用整合連絡人存放區，請在命令列輸入：</span><span class="sxs-lookup"><span data-stu-id="44c46-111">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="44c46-112">若要針對特定網站的使用者啟用整合連絡人存放區，請在命令列輸入：</span><span class="sxs-lookup"><span data-stu-id="44c46-112">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="44c46-113">例如：</span><span class="sxs-lookup"><span data-stu-id="44c46-113">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="44c46-114">若要啟用租使用者的整合連絡人存放區，請在命令列輸入：</span><span class="sxs-lookup"><span data-stu-id="44c46-114">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="44c46-115">例如：</span><span class="sxs-lookup"><span data-stu-id="44c46-115">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="44c46-116">若要針對特定使用者啟用整合連絡人存放區，請在命令列輸入：</span><span class="sxs-lookup"><span data-stu-id="44c46-116">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="44c46-117">您也可以使用使用者別名或 SIP URI，而不是使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="44c46-117">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="44c46-118">例如：</span><span class="sxs-lookup"><span data-stu-id="44c46-118">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="44c46-119">在前面的範例中，第一個命令會建立名為 [ <EM>UCS</EM> ] 的新使用者原則，並將 UcsAllowed 標誌設定為 True。</span><span class="sxs-lookup"><span data-stu-id="44c46-119">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="44c46-120">第二個命令會將原則指派給使用者，並使用顯示名稱 Ken Myer，這表示現在已為整合連絡人存放區啟用 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="44c46-120">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

