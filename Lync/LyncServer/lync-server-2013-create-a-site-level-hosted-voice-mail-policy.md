---
title: Lync Server 2013：建立網站層級主控語音信箱原則
description: Lync Server 2013：建立網站層級主控語音信箱原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd578359a8d20562e8887b61b86d53332e6f8d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578369"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="526b4-103">在 Lync Server 2013 中建立網站層級主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="526b4-103">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="526b4-104">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="526b4-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="526b4-p101">「網站」\*\* 原則會影響定義該原則之網站上所屬的全部使用者。如果使用者已針對主控 Exchange UM 存取進行設定，且未獲指派個別使用者原則，便會套用網站原則。如果您尚未部署網站原則，則會套用全域原則。</span><span class="sxs-lookup"><span data-stu-id="526b4-p101">A *site* policy can impact all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies. If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="526b4-108">如需設定網站原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="526b4-108">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="526b4-109">新 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="526b4-109">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="526b4-110">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="526b4-110">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="526b4-111">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="526b4-111">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="526b4-112">建立網站主控的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="526b4-112">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="526b4-113">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="526b4-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="526b4-p102">執行 New-CsHostedVoicemailPolicy Cmdlet，建立原則。例如，執行：</span><span class="sxs-lookup"><span data-stu-id="526b4-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="526b4-116">此範例會建立網站範圍的主控語音信箱原則，並設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="526b4-116">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="526b4-117">**Identity** 指定原則的唯一識別碼，包含範圍。</span><span class="sxs-lookup"><span data-stu-id="526b4-117">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="526b4-118">針對具有網站範圍的原則，Identity 參數值必須以格式指定 `site:` *\<name\>* ，例如 `site:Redmond` 。</span><span class="sxs-lookup"><span data-stu-id="526b4-118">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="526b4-p104">**Destination** 指定主控之 Exchange UM 服務的完整網域名稱 (FQDN)。此參數是選用的，但如果您企圖啟用使用者的主控語音信箱，且指派給使用者的原則沒有 Destination 值，則啟用作業會失敗。</span><span class="sxs-lookup"><span data-stu-id="526b4-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="526b4-121">**Description** 提供關於原則的選用說明資訊。</span><span class="sxs-lookup"><span data-stu-id="526b4-121">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="526b4-122">**組織** 指定家用 Lync Server 2013 使用者之 Exchange 承租人的逗號分隔清單。</span><span class="sxs-lookup"><span data-stu-id="526b4-122">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="526b4-123">必須以主控之 Exchange UM 服務上的租用戶之 FQDN 來指定每一個租用戶。</span><span class="sxs-lookup"><span data-stu-id="526b4-123">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

