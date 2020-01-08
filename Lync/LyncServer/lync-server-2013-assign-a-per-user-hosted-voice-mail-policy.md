---
title: Lync Server 2013：指派每位使用者託管的語音信箱原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2202e1b4c03eb25d12e46c3a533313a54bc76c4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977134"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="1d9d4-102">在 Lync Server 2013 中指派每個使用者託管的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="1d9d4-102">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="1d9d4-103">部署一或多個以使用者為宿主的語音信箱原則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="1d9d4-103">Deploying one or more per-user hosted voice mail policies is optional.</span></span> <span data-ttu-id="1d9d4-104">如果您要部署每個使用者的原則，您必須將它們明確指派給使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="1d9d4-104">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="1d9d4-105">如需指派或移除依使用者託管語音信箱原則指派或移除作業的詳細資料，請參閱下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="1d9d4-105">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="1d9d4-106">授與 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="1d9d4-106">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="1d9d4-107">移除-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="1d9d4-107">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="1d9d4-108">指派每位使用者託管的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="1d9d4-108">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="1d9d4-109">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1d9d4-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1d9d4-110">執行授與 CsHostedVoicemailPolicy Cmdlet，將每位使用者託管的語音信箱原則指派給個別的使用者、群組和連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="1d9d4-110">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects.</span></span> <span data-ttu-id="1d9d4-111">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="1d9d4-111">For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="1d9d4-112">這個範例已將 ExRedmond 託管的語音信箱原則指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="1d9d4-112">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="1d9d4-113">身分**識別**指定要修改的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1d9d4-113">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="1d9d4-114">身分識別值可以使用下列任何一種格式加以指定：</span><span class="sxs-lookup"><span data-stu-id="1d9d4-114">The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="1d9d4-115">使用者的 SIP 位址</span><span class="sxs-lookup"><span data-stu-id="1d9d4-115">The user's SIP address</span></span>
    
      - <span data-ttu-id="1d9d4-116">使用者的 Active Directory 使用者主要名稱</span><span class="sxs-lookup"><span data-stu-id="1d9d4-116">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="1d9d4-117">使用者的網域\\登入名稱（例如 contoso\\kenmyer）</span><span class="sxs-lookup"><span data-stu-id="1d9d4-117">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="1d9d4-118">使用者的 Active Directory 網域服務顯示名稱（例如，Ken Myer）。</span><span class="sxs-lookup"><span data-stu-id="1d9d4-118">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="1d9d4-119">如果使用顯示名稱作為身分識別值，您可以使用星號（\*）萬用字元。</span><span class="sxs-lookup"><span data-stu-id="1d9d4-119">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="1d9d4-120">例如，恒等 "\* smith" 會傳回其顯示名稱以字串值 "smith" 結尾的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="1d9d4-120">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="1d9d4-121">使用者的 Active Directory SAM-帳戶名稱不能用來做為身分識別值，因為 SAM-帳戶名稱在林中不一定是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1d9d4-121">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


