---
title: Lync Server 2013： 建立個別使用者裝載語音信箱原則
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
ms.openlocfilehash: 055d65fe691d99c8b960ebed088ba47cbcb2f988
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="e6b4c-102">在 Lync Server 2013 中建立個別使用者裝載語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="e6b4c-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6b4c-103">_**主題上次修改日期：** 2012年-09-24_</span><span class="sxs-lookup"><span data-stu-id="e6b4c-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="e6b4c-104">*「個別使用者的」* 原則只會影響個別使用者、群組和連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="e6b4c-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="e6b4c-105">若要部署個別使用者的原則，您必須明確指派原則給一個或多個使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="e6b4c-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="e6b4c-106">如需詳細資訊，請參閱[指派 Lync Server 2013 中的個別使用者裝載語音信箱原則](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b4c-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="e6b4c-107">如需使用個別使用者裝載語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面文件的下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e6b4c-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="e6b4c-108">新 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="e6b4c-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="e6b4c-109">Set-cshostedvoicemailpolicy</span><span class="sxs-lookup"><span data-stu-id="e6b4c-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="e6b4c-110">Get-cshostedvoicemailpolicy</span><span class="sxs-lookup"><span data-stu-id="e6b4c-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="e6b4c-111">若要建立個別使用者的裝載語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="e6b4c-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="e6b4c-112">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="e6b4c-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e6b4c-p102">執行 New-CsHostedVoicemailPolicy Cmdlet，建立原則。例如，執行：</span><span class="sxs-lookup"><span data-stu-id="e6b4c-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="e6b4c-115">上述範例會建立個別使用者範圍的裝載語音信箱原則，並設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="e6b4c-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="e6b4c-p103">**Identity** 指定原則的唯一識別碼，包含範圍。若是個別使用者範圍的原則，此參數值必須以單一字串格式指定，例如 ExRedmond。</span><span class="sxs-lookup"><span data-stu-id="e6b4c-p103">**Identity** specifies a unique identifier for the policy, which includes the scope. For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="e6b4c-p104">**Destination** 指定主控之 Exchange UM 服務的完整網域名稱 (FQDN)。此參數是選用的，但如果您企圖啟用使用者的主控語音信箱，且指派給使用者的原則沒有 Destination 值，則啟用作業會失敗。</span><span class="sxs-lookup"><span data-stu-id="e6b4c-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="e6b4c-120">**Description** 提供關於原則的選用說明資訊。</span><span class="sxs-lookup"><span data-stu-id="e6b4c-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="e6b4c-121">**Organization**指定以逗號分隔清單中的 Exchange 承租人該隸屬的 Lync Server 2013 使用者。</span><span class="sxs-lookup"><span data-stu-id="e6b4c-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="e6b4c-122">必須以主控之 Exchange UM 服務上的租用戶之 FQDN 來指定每一個租用戶。</span><span class="sxs-lookup"><span data-stu-id="e6b4c-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e6b4c-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e6b4c-123">See Also</span></span>


[<span data-ttu-id="e6b4c-124">指派 Lync Server 2013 中的個別使用者裝載語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="e6b4c-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

