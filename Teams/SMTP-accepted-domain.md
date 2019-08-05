---
title: 在 Exchange Online 中新增 Microsoft 團隊 SMTP 網域作為允許的寄件者網域
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: 瞭解如何將 Microsoft 團隊 SMTP 網域新增為 Exchange Online 中的 [允許的寄件者] 網域, 以傳送通知給小組成員。
appliesto:
- Microsoft Teams
ms.openlocfilehash: dcd4fe932d70cfacb3a4856fae68a5a1a81a94ad
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2019
ms.locfileid: "36183993"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>在 Exchange Online 中新增 Microsoft 團隊 SMTP 網域作為允許的寄件者網域 
=============================================================================

無論您是在系統管理主控台中建立 Office 365 群組, 還是使用 Outlook, 都會使用 Exchange Online 傳送小組成員新增至群組的通知。 這些訊息是從您的租使用者產生的, 因為它們代表您的預設網域 SMTP FQDN。

![顯示已新增至群組之使用者之訊息標頭的螢幕擷取畫面。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

小組也會使用 Microsoft Exchange Online 來傳送通知給小組成員 (如果已新增)。 這是 SMTP 郵件網域 FQDN 的差異 @email 為「teams.microsoft.com」 (針對商業/商業租使用者) 和「@GCC-email.teams.com」 (適用于政府租使用者), 並可透過垃圾郵件篩選功能來捕獲。

![顯示已新增至群組之使用者之訊息標頭的螢幕擷取畫面。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

為了獲得最佳結果和無縫操作, 請考慮將 Microsoft 團隊 SMTP 網域新增至 Exchange Online 垃圾郵件設定中的 [允許的寄件者網域] 清單:

![垃圾郵件設定設定的 [允許清單] 區段的螢幕擷取畫面](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
