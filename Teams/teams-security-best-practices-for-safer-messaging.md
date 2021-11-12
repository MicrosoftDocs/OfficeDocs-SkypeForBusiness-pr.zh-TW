---
title: 更安全傳訊的 Teams 安全性最佳做法
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 11/10/2021
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: 本文提供如何安全地使用 Teams 的快速參考，可做為一般安全性最佳作法的入門，以及訓練使用者進行安全傳訊的提示。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61ba1607f2999ef56c3176d4ba8ed0aaebb82e50
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909676"
---
# <a name="security-best-practices-for-microsoft-teams"></a>Microsoft Teams 的安全性最佳作法

透過立即訊息和視訊會議進行共同作業，使得許多產業和學校在疫情爆發期間能夠繼續工作。 不過，這類大規模線上即時共同作業也都附帶必須解決的 *風險*。 否則，不良執行者會利用在工作和生活中的這項變更，進行 **網路釣魚** 和 **垃圾郵件** 行銷活動。 本文中的編號參考清單可做為使用 Teams 傳送訊息給其他人時一般安全性的入門，也是適用於 Teams 新使用者或任何立即傳訊安全性的訓練指導方針。

電子郵件中存在的相同網路釣魚風險也存在於立即訊息和共同作業應用程式中，因此應該套用相同的使用者意識和指導方針來保護 Teams 使用者。

在使用者層級，有些措施可能很簡單，而且使用者應該感到可以信賴它們。 使用者不應該按一下以開啟來自任何他們不認識的人或無法根據文章[保護自己防範網路釣魚](https://support.microsoft.com/en-us/windows/protect-yourself-from-phishing-0c7ea947-ba98-3bd9-7184-430e1f860a44)來驗證其身分識別的人的連結。 此外，為了防範外部攻擊，針對[管理外部存取 (同盟) - Microsoft Teams | Microsoft Docs](/microsoftteams/manage-external-access)，租用戶系統管理員可以停用或關閉企業同盟和 Teams for Life (TFL) 和 Skype 互通性。

Teams 共同作業功能集可實現傳訊、檔案共同作業、會議、白板，以及許多其他交流的機會。 這些功能適用於 Teams for Enterprise、Teams for Life、Skype、商務用 Skype、Azure 通訊服務 (ACS) 等等。 這也表示必須跨這些功能的廣度，全面保護您自己、同儕和您的客戶。 在這裡重申，每個使用者都應該感到可以為自己、其同儕和其客戶做出最安全的決策。

## <a name="just-as-with-email-online-safety-must-be-practiced-in-microsoft-teams-messaging"></a>就像電子郵件一樣，Microsoft Teams 傳訊中必須實作線上安全

在 Teams 中工作時，標準安全措施應該變得根深蒂固。

1. 對來自組織外部的連絡人和會議要求保持警覺。 陌生人可能是好人。 而有些人可能暗中危害。
2. 如果您不認得該寄件者，您可以檢查公司的已知全域通訊清單是否有其身分識別，並且將任何您無法驗證的通訊呈報到較高層級進行處理。 有疑問時，請勿與未知和未經驗證的使用者互動。
3. 如果您收到來自未知人員的連結或檔案，請不要點按。 重申，請為您自己，並為其他使用者以及客戶的安全使用您的最佳判斷。
4. 如果按一下的連結瀏覽將您登陸在安全連結頁面上，在其中您被封鎖而無法瀏覽，請勿嘗試規避該頁面 (對於可能最後抵達紅色、封鎖安全附件頁面的任何點按附件也一樣)。 如果您知道並信任目標網站，請向 Microsoft 和引導您到該處的人報告該問題。 但登陸封鎖頁面可能有許多原因，而且應該考慮使用紅色旗標，而不是規避瀏覽。
5. 絕不將個人資訊提供給任何來路不明的要求。 這也對個人安全有風險。 攻擊者可能會利用與您生日一樣簡單的詳細資料。
6. 掃描您的連結，尋找是否有拼字錯誤、增加的數字或奇怪的字元。 您可能預期為 `www.litware.com/strategies/Metricsbreakout.xlsx` 的連結，但發現位址看起來像是 `www.litwre.com`、`www.litwarecom.com` 或甚至是 `www.litwαre.com`。 如果您不認得該連結，請保持懷疑。 位址 `www.litware.com` 與 `www.litware2021.com` 不同。

您必須維持您的安全，而不要輕率地對待您的安全性，以及您合作的人員的安全性，或視為理所當然。 身為個別使用者，在信任之前，您應該一直感到可以透過驗證來保護您自己、您的同儕和客戶。

最後，要承認每個人都會出錯也非常重要。 使用者可能很容易在很急切時 (舉例來說)，或疲累時點按。 系統管理員應該確定呈報問題連結點按次數和其他安全性事件的資源，可讓其組織的使用者清楚了解，如此一來，如果發生錯誤，使用者已救助，並且可以採取進一步的安全性動作。

> [!TIP]
> 檢查您不確定的任何連絡人的設定檔卡片，特別是如果該電子郵件是公司外部的連絡人 (例如，如果組織不是 *Litware*，則是結尾為 *@litware.com* 的帳戶)。 使用者可以檢查 **(GUEST)** 的設定檔卡片，以驗證他們不認識的人員是否為會議歡迎的來賓。 來賓會明確獲邀參與。