---
title: Lync Server 2013：建立每位使用者託管的語音信箱原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d09638c28c1cbd2b068972aff169376508325885
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="80d15-102">在 Lync Server 2013 中建立每使用者託管的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="80d15-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80d15-103">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="80d15-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="80d15-104">*每個使用者*的原則只會影響個別的使用者、群組和連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="80d15-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="80d15-105">若要部署每個使用者的原則，您必須將原則明確指派給一或多個使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="80d15-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="80d15-106">如需詳細資訊，請參閱[在 Lync Server 2013 中指派每個使用者託管的語音信箱原則](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="80d15-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="80d15-107">如需有關使用每個使用者託管語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="80d15-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="80d15-108">新-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="80d15-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="80d15-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="80d15-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="80d15-110">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="80d15-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="80d15-111">若要建立每位使用者託管的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="80d15-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="80d15-112">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="80d15-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="80d15-113">執行新的 CsHostedVoicemailPolicy Cmdlet 來建立原則。</span><span class="sxs-lookup"><span data-stu-id="80d15-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="80d15-114">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="80d15-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="80d15-115">前面的範例會建立含每個使用者範圍的託管語音信箱原則，並設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="80d15-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="80d15-116">身分**識別**會指定原則的唯一識別碼，包括範圍。</span><span class="sxs-lookup"><span data-stu-id="80d15-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="80d15-117">針對具有每使用者範圍的原則，此參數值是指定為簡單字串，例如 ExRedmond。</span><span class="sxs-lookup"><span data-stu-id="80d15-117">For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="80d15-118">**Destination**指定託管 Exchange UM 服務的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="80d15-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="80d15-119">這個參數是選用的，但如果您嘗試啟用託管語音信箱的使用者，且使用者指派的原則沒有目的地值，enable 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="80d15-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="80d15-120">**描述**提供原則的選用描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="80d15-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="80d15-121">[**組織**]：指定家用 Lync Server 2013 使用者的 Exchange 租使用者清單（以逗號分隔）。</span><span class="sxs-lookup"><span data-stu-id="80d15-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="80d15-122">每個租使用者都必須在託管 Exchange UM 服務上指定為該租使用者的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="80d15-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="80d15-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="80d15-123">See Also</span></span>


[<span data-ttu-id="80d15-124">在 Lync Server 2013 中指派每個使用者託管的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="80d15-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

