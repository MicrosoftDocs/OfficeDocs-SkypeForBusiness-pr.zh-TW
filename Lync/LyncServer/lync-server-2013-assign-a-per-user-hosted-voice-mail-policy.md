---
title: Lync Server 2013：指派每位使用者的主控語音信箱原則
description: Lync Server 2013：指派每位使用者的主控語音信箱原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559889"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="a766a-103">在 Lync Server 2013 中指派每位使用者的主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="a766a-103">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="a766a-104">部署一或多個個別使用者主控語音信箱原則是選用的。</span><span class="sxs-lookup"><span data-stu-id="a766a-104">Deploying one or more per-user hosted voice mail policies is optional.</span></span> <span data-ttu-id="a766a-105">如果您選擇部署個別使用者原則，則必須明確指派原則給使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="a766a-105">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="a766a-106">如需指派或移除個別使用者主控語音信箱原則指派的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a766a-106">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="a766a-107">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a766a-107">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="a766a-108">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a766a-108">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="a766a-109">指派個別使用者主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="a766a-109">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="a766a-110">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="a766a-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a766a-111">執行 Grant-CsHostedVoicemailPolicy Cmdlet，將每位使用者的裝載語音信箱原則指派給個別使用者、群組和連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="a766a-111">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects.</span></span> <span data-ttu-id="a766a-112">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="a766a-112">For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="a766a-113">這個範例會將 ExRedmond 主控語音信箱原則指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="a766a-113">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="a766a-114">**Identity** 指定要修改的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a766a-114">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="a766a-115">您可以使用下列任何格式指定 Identity 值：</span><span class="sxs-lookup"><span data-stu-id="a766a-115">The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="a766a-116">使用者的 SIP 位址</span><span class="sxs-lookup"><span data-stu-id="a766a-116">The user's SIP address</span></span>
    
      - <span data-ttu-id="a766a-117">使用者的 Active Directory 使用者主體名稱</span><span class="sxs-lookup"><span data-stu-id="a766a-117">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="a766a-118">使用者的網域 \\ 登入名稱 (例如，contoso \\ kenmyer) </span><span class="sxs-lookup"><span data-stu-id="a766a-118">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="a766a-119">使用者的 Active Directory 網域服務 Display-Name (例如 Ken Myer) 。</span><span class="sxs-lookup"><span data-stu-id="a766a-119">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="a766a-120">如果使用 Display-Name 做為 Identity 值，您可以使用星號 (\*) 萬用字元。</span><span class="sxs-lookup"><span data-stu-id="a766a-120">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="a766a-121">例如，身分識別 " \* smith" 會傳回 Display-Name 以字串值 "smith" 結尾的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="a766a-121">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="a766a-122">使用者的 Active Directory SAM 帳戶名稱不能做為身分識別值，因為 SAM 帳戶名稱在樹系中不一定是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a766a-122">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


