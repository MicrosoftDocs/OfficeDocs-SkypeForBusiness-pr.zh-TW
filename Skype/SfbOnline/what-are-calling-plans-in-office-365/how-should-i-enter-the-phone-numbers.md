---
title: 我應該如何輸入電話號碼？
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: '瞭解如何在將電話號碼移植到商務用 Skype 時，設定電話號碼。 '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "37642606"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="8787e-103">我應該如何輸入電話號碼？</span><span class="sxs-lookup"><span data-stu-id="8787e-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="8787e-104">當您要移植電話號碼時，必須以正確的格式輸入。</span><span class="sxs-lookup"><span data-stu-id="8787e-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8787e-105">每個電話號碼或電話號碼範圍必須在每一行上分別輸入。</span><span class="sxs-lookup"><span data-stu-id="8787e-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="8787e-106">輸入單一電話號碼時：</span><span class="sxs-lookup"><span data-stu-id="8787e-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="8787e-107">所有特殊字元都會被忽略（包括破折號 "-"）。</span><span class="sxs-lookup"><span data-stu-id="8787e-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="8787e-108">例如：</span><span class="sxs-lookup"><span data-stu-id="8787e-108">For example:</span></span>
    
  - <span data-ttu-id="8787e-109">10位數的數位： \*\* &amp; \*（\*425 （\*&amp;）（&amp;\*4 （））（\*250649\*\*將修正為 **+ 14255550649**）。</span><span class="sxs-lookup"><span data-stu-id="8787e-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="8787e-110">對於11位數的數位： **1\*（）（\*&amp;&amp;\*42 （）\*&amp;（55550649**將修正為 **+ 14255550649**）。</span><span class="sxs-lookup"><span data-stu-id="8787e-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="8787e-111">如果有10或11個數字，所有標記都會被忽略。</span><span class="sxs-lookup"><span data-stu-id="8787e-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="8787e-112">例如， \*\* \<div> 4255551234\</div>\*\* 將會是 **+ 14255551234**。</span><span class="sxs-lookup"><span data-stu-id="8787e-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="8787e-113">"-"、空格和括弧將會被忽略。</span><span class="sxs-lookup"><span data-stu-id="8787e-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="8787e-114">例如：</span><span class="sxs-lookup"><span data-stu-id="8787e-114">For example:</span></span>
    
  - <span data-ttu-id="8787e-115">10位數的數位： **（425） 555-6776**將修正為 **+ 14255556776**。</span><span class="sxs-lookup"><span data-stu-id="8787e-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="8787e-116">如果是11位數的數位： **1 （425） 555-6776**將修正為 **+ 14255556776**。</span><span class="sxs-lookup"><span data-stu-id="8787e-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="8787e-117">如果有10位數或11位數的電話號碼，所有字母都會被視為特殊字元，而且會略過。</span><span class="sxs-lookup"><span data-stu-id="8787e-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="8787e-118">例如：</span><span class="sxs-lookup"><span data-stu-id="8787e-118">For example:</span></span>
    
  - <span data-ttu-id="8787e-119">10位數的數位： **14jaosia2reoij05jof55506ajfoj49isdjf**將會修正為 **+ 14255550649**。</span><span class="sxs-lookup"><span data-stu-id="8787e-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="8787e-120">針對11位數的數位： **1ade4jaoda2rfoij05ojof55506dsfoj49if**將修正為 **+ 14255550649**。</span><span class="sxs-lookup"><span data-stu-id="8787e-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="8787e-121">任何特殊字元組合（甚至在其他語言中）都將得到修正。</span><span class="sxs-lookup"><span data-stu-id="8787e-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="8787e-122">例如：</span><span class="sxs-lookup"><span data-stu-id="8787e-122">For example:</span></span> 
    
  - <span data-ttu-id="8787e-123">10位數的數位：**中文4中文2ajj5\*（）（\*（5（） .。。551345**將修正為 **+ 14555551345**。</span><span class="sxs-lookup"><span data-stu-id="8787e-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="8787e-124">針對11位數的數位：**中文4中文 2\*$ a5 （）（\*（5（） .。。55（. 1345**將修正為 **+ 14555551345**。</span><span class="sxs-lookup"><span data-stu-id="8787e-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="8787e-125">如果有任何號碼少於10位數或超過11位數，則會醒目提示這些數位，讓使用者修正：</span><span class="sxs-lookup"><span data-stu-id="8787e-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="8787e-126">\*\*5551245\* \*將會醒目提示，且需要修正。</span><span class="sxs-lookup"><span data-stu-id="8787e-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="8787e-127">**1234567891011**將會醒目提示，且需要修正。</span><span class="sxs-lookup"><span data-stu-id="8787e-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="8787e-128">任何少於10位數或超過11位數的數位（含任何特殊字元）都將醒目提示，而不會自動修正。</span><span class="sxs-lookup"><span data-stu-id="8787e-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="8787e-129">對於不是輸入之特殊字元的7位數數位： **123456abcdefg7**將會醒目提示，且需要加以修正，但不會忽略字母。</span><span class="sxs-lookup"><span data-stu-id="8787e-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="8787e-130">如果您使用的是已輸入之特殊字元的7位數數位： **12345！ @ # $&amp;\*% ^ （）--@ # $&amp;\*% ^ （） 7**將會醒目提示以加以修正。</span><span class="sxs-lookup"><span data-stu-id="8787e-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="8787e-131">特殊字元不會被忽略。</span><span class="sxs-lookup"><span data-stu-id="8787e-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="8787e-132">當您輸入電話號碼的範圍時。</span><span class="sxs-lookup"><span data-stu-id="8787e-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="8787e-133">只允許兩個電話號碼。</span><span class="sxs-lookup"><span data-stu-id="8787e-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="8787e-134">較小的數位必須是範圍中的第一個數位。</span><span class="sxs-lookup"><span data-stu-id="8787e-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="8787e-135">所有特殊字元（除破折號 "-" 之外）都被視為與單一數位相同。</span><span class="sxs-lookup"><span data-stu-id="8787e-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="8787e-136">例如， **（425） 555 0&amp;\*（123-（1425） 5557899nm**將修正為 **+ 14255550123-+ 13202040659**。</span><span class="sxs-lookup"><span data-stu-id="8787e-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="8787e-137">"-" 只用于分隔兩個數字。</span><span class="sxs-lookup"><span data-stu-id="8787e-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="8787e-138">不支援在數位範圍中包含多個 "-"。</span><span class="sxs-lookup"><span data-stu-id="8787e-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="8787e-139">例如， **（425） 555-0649-（425） 555-1115**應該輸入為 **（425） 5550649-（425） 5551115**。</span><span class="sxs-lookup"><span data-stu-id="8787e-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
  <span data-ttu-id="8787e-140">**如需完整的逐步指示，請參閱[將電話號碼轉接至 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365)。**</span><span class="sxs-lookup"><span data-stu-id="8787e-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

  > [!NOTE]
  > <span data-ttu-id="8787e-141">如果您需要取得更多的電話號碼，請[聯絡商務產品支援-系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="8787e-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="8787e-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="8787e-142">Related topics</span></span>
[<span data-ttu-id="8787e-143">傳送電話號碼常見問題</span><span class="sxs-lookup"><span data-stu-id="8787e-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="8787e-144">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="8787e-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="8787e-145">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="8787e-145">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="8787e-146">緊急通話條款與條件</span><span class="sxs-lookup"><span data-stu-id="8787e-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="8787e-147">[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8787e-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 