---
title: Lync Server 2013：建立每位使用者的主控語音信箱原則
description: Lync Server 2013：建立每位使用者的主控語音信箱原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de528ceb9bc01114948c276c27f99039658aee38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563189"
---
# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="5a4c8-103">在 Lync Server 2013 中建立個別使用者的主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="5a4c8-103">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a4c8-104">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="5a4c8-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="5a4c8-105">*「個別使用者的」* 原則只會影響個別使用者、群組和連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="5a4c8-105">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="5a4c8-106">若要部署個別使用者的原則，您必須明確指派原則給一個或多個使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="5a4c8-106">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="5a4c8-107">如需詳細資訊，請參閱 [在 Lync Server 2013 中指派每位使用者的主控語音信箱原則](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="5a4c8-107">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="5a4c8-108">如需使用個別使用者主控語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5a4c8-108">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="5a4c8-109">新 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5a4c8-109">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="5a4c8-110">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5a4c8-110">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="5a4c8-111">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5a4c8-111">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="5a4c8-112">若要建立個別使用者的裝載語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="5a4c8-112">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="5a4c8-113">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="5a4c8-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5a4c8-p102">執行 New-CsHostedVoicemailPolicy Cmdlet，建立原則。例如，執行：</span><span class="sxs-lookup"><span data-stu-id="5a4c8-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="5a4c8-116">上述範例會建立個別使用者範圍的裝載語音信箱原則，並設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="5a4c8-116">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="5a4c8-p103">**Identity** 指定原則的唯一識別碼，包含範圍。若是個別使用者範圍的原則，此參數值必須以單一字串格式指定，例如 ExRedmond。</span><span class="sxs-lookup"><span data-stu-id="5a4c8-p103">**Identity** specifies a unique identifier for the policy, which includes the scope. For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="5a4c8-p104">**Destination** 指定主控之 Exchange UM 服務的完整網域名稱 (FQDN)。此參數是選用的，但如果您企圖啟用使用者的主控語音信箱，且指派給使用者的原則沒有 Destination 值，則啟用作業會失敗。</span><span class="sxs-lookup"><span data-stu-id="5a4c8-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="5a4c8-121">**Description** 提供關於原則的選用說明資訊。</span><span class="sxs-lookup"><span data-stu-id="5a4c8-121">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="5a4c8-122">**組織** 指定家用 Lync Server 2013 使用者之 Exchange 承租人的逗號分隔清單。</span><span class="sxs-lookup"><span data-stu-id="5a4c8-122">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="5a4c8-123">必須以主控之 Exchange UM 服務上的租用戶之 FQDN 來指定每一個租用戶。</span><span class="sxs-lookup"><span data-stu-id="5a4c8-123">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5a4c8-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5a4c8-124">See Also</span></span>


[<span data-ttu-id="5a4c8-125">在 Lync Server 2013 中指派每位使用者的主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="5a4c8-125">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

