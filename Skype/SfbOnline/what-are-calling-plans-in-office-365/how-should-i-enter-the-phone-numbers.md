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
# <a name="how-should-i-enter-the-phone-numbers"></a>我應該如何輸入電話號碼？

當您要移植電話號碼時，必須以正確的格式輸入。 
  
> [!NOTE]
> 每個電話號碼或電話號碼範圍必須在每一行上分別輸入。 
  
- 輸入單一電話號碼時：
    
  - 所有特殊字元都會被忽略（包括破折號 "-"）。 例如：
    
  - 10位數的數位： ** &amp; \*（\*425 （\*&amp;）（&amp;\*4 （））（\*250649**將修正為 **+ 14255550649**）。
    
  - 對於11位數的數位： **1\*（）（\*&amp;&amp;\*42 （）\*&amp;（55550649**將修正為 **+ 14255550649**）。
    
  - 如果有10或11個數字，所有標記都會被忽略。 例如， ** \<div> 4255551234\</div>** 將會是 **+ 14255551234**。
    
  - "-"、空格和括弧將會被忽略。 例如：
    
  - 10位數的數位： **（425） 555-6776**將修正為 **+ 14255556776**。
    
  - 如果是11位數的數位： **1 （425） 555-6776**將修正為 **+ 14255556776**。
    
  - 如果有10位數或11位數的電話號碼，所有字母都會被視為特殊字元，而且會略過。 例如：
    
  - 10位數的數位： **14jaosia2reoij05jof55506ajfoj49isdjf**將會修正為 **+ 14255550649**。
    
  - 針對11位數的數位： **1ade4jaoda2rfoij05ojof55506dsfoj49if**將修正為 **+ 14255550649**。
    
  - 任何特殊字元組合（甚至在其他語言中）都將得到修正。 例如： 
    
  - 10位數的數位：**中文4中文2ajj5\*（）（\*（5（） .。。551345**將修正為 **+ 14555551345**。
    
  - 針對11位數的數位：**中文4中文 2\*$ a5 （）（\*（5（） .。。55（. 1345**將修正為 **+ 14555551345**。
    
  - 如果有任何號碼少於10位數或超過11位數，則會醒目提示這些數位，讓使用者修正：
    
  - \*\*5551245\* \*將會醒目提示，且需要修正。
    
  - **1234567891011**將會醒目提示，且需要修正。
    
  - 任何少於10位數或超過11位數的數位（含任何特殊字元）都將醒目提示，而不會自動修正。
    
  - 對於不是輸入之特殊字元的7位數數位： **123456abcdefg7**將會醒目提示，且需要加以修正，但不會忽略字母。
    
  - 如果您使用的是已輸入之特殊字元的7位數數位： **12345！ @ # $&amp;\*% ^ （）--@ # $&amp;\*% ^ （） 7**將會醒目提示以加以修正。 特殊字元不會被忽略。
    
- 當您輸入電話號碼的範圍時。
    
  - 只允許兩個電話號碼。 較小的數位必須是範圍中的第一個數位。
    
  - 所有特殊字元（除破折號 "-" 之外）都被視為與單一數位相同。 例如， **（425） 555 0&amp;\*（123-（1425） 5557899nm**將修正為 **+ 14255550123-+ 13202040659**。
    
  - "-" 只用于分隔兩個數字。 不支援在數位範圍中包含多個 "-"。 例如， **（425） 555-0649-（425） 555-1115**應該輸入為 **（425） 5550649-（425） 5551115**。
    
  **如需完整的逐步指示，請參閱[將電話號碼轉接至 Office 365](/microsoftteams/transfer-phone-numbers-to-office-365)。**

  > [!NOTE]
  > 如果您需要取得更多的電話號碼，請[聯絡商務產品支援-系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

  
## <a name="related-topics"></a>相關主題
[傳送電話號碼常見問題](/microsoftteams/transferring-phone-numbers-common-questions)

[通話方案所用的不同類型的電話號碼](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話條款與條件](/microsoftteams/emergency-calling-terms-and-conditions)

[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 