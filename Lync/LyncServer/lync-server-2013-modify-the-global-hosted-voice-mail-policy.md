---
title: Lync Server 2013：修改全域主控語音信箱原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d0e29981df18ed883d6c33fb810d86da09d255
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="184b2-102">在 Lync Server 2013 中修改全域主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="184b2-102">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="184b2-103">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="184b2-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="184b2-104">*通用*主控語音信箱原則是隨 Lync Server 2013 一起安裝。</span><span class="sxs-lookup"><span data-stu-id="184b2-104">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="184b2-105">您可以修改它以符合您的需求，但是您無法重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="184b2-105">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="184b2-106">若要修改全域原則，您可以使用 CsHostedVoicemailPolicy 指令程式，將參數設定為特定部署的適當值。</span><span class="sxs-lookup"><span data-stu-id="184b2-106">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="184b2-107">如需[CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="184b2-107">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="184b2-108">修改全域主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="184b2-108">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="184b2-109">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="184b2-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="184b2-110">執行 CsHostedVoicemailPolicy 指令程式，為您的環境設定全域原則參數。</span><span class="sxs-lookup"><span data-stu-id="184b2-110">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="184b2-111">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="184b2-111">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="184b2-112">因為此命令不會指定原則的 Identity 參數，所以 Windows PowerShell 命令列介面會設定全域主控語音信箱原則的下列值：</span><span class="sxs-lookup"><span data-stu-id="184b2-112">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="184b2-p103">**Destination** 指定主控之 Exchange UM 服務的完整網域名稱 (FQDN)。此參數是選用的，但如果您企圖啟用使用者的主控語音信箱，且指派給使用者的原則沒有 Destination 值，則啟用作業會失敗。</span><span class="sxs-lookup"><span data-stu-id="184b2-p103">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="184b2-115">**組織**指定家用 Lync Server 使用者之 Exchange 承租人的逗號分隔清單。</span><span class="sxs-lookup"><span data-stu-id="184b2-115">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="184b2-116">必須以主控之 Exchange UM 服務上的租用戶之 FQDN 來指定每一個租用戶。</span><span class="sxs-lookup"><span data-stu-id="184b2-116">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="184b2-117">在前面的範例 Cmdlet 中，值 "corp1.litwareinc.com" 會取代可能已存在於組織參數中的任何值。</span><span class="sxs-lookup"><span data-stu-id="184b2-117">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter.</span></span> <span data-ttu-id="184b2-118">例如，如果原則已包含以逗號分隔的組織清單，則會取代完整清單。</span><span class="sxs-lookup"><span data-stu-id="184b2-118">For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced.</span></span> <span data-ttu-id="184b2-119">如果您想要將組織新增至清單，而不是取代整個清單，請執行類似下列的命令。</span><span class="sxs-lookup"><span data-stu-id="184b2-119">If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

