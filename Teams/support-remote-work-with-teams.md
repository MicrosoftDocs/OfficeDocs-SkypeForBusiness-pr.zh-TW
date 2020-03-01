---
title: 支援使用 Microsoft Teams 的遠端工作者
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: dansteve
localization_priority: Priority
search.appverid: MET150
description: 使用本指導方針來協助組織中的遠端工作者使用 Microsoft Teams 來提高生產力，尤其是當他們在家中工作 (WFH) 時，以因應 COVID-19 (冠狀病毒) 爆發的情況。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fbdb875896ca07402d699f1ca2a28770cb46ee2
ms.sourcegitcommit: ae65fb089d98665c4b26e0345bb96241fb893f0b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/29/2020
ms.locfileid: "42342900"
---
# <a name="support-remote-workers-using-microsoft-teams"></a>支援使用 Microsoft Teams 的遠端工作者

使用本文中的最佳做法，為遠端或在家工作者提供支援。

## <a name="technical"></a>技術

1.  確定[所有人均開啟 Teams](assign-teams-licenses.md)
    
      - 查看 [Teams Exploratory](teams-exploratory.md) 或 [Teams 免費版](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c)，讓公司中所有人都能使用 Teams。

      - 遠端員工更仰賴會議和音訊會議。 如果您還沒有推出這些工作負載，請查看 [Teams 中的會議和研討會](deploy-meetings-microsoft-teams-landing-page.md)。

2.  向您的使用者介紹 Teams。 下載 [Teams 客戶成功案例套件](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip)，取得簡報、範例電子郵件、海報和入門指南。


5.  確定您的員工擁有足夠的網際網路存取權和頻寬供 Teams 使用。 使用[針對 Teams 準備組織的網路](prepare-network.md)中的指導方針，以了解如何執行此作業。
    - 有限的頻寬會影響 Teams 會議中的音訊品質。 為了確保在低頻寬條件下的最佳會議體驗，請鼓勵使用者限制視訊通話，並對通話和會議音訊使用 PSTN。 

    - 如果您需要協助疑難排解或修正有關通話或會議品質的問題，請遵循本文最下方的[已知問題：撥入商務用 Skype 或 Teams 會議識別碼](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids)中的指導方針。

2.  [傳送訓練連結](enduser-training.md)，協助您的員工充分發揮 Teams 的效用。
    
3. 閱讀有關遠端工作的新內容，並與您的使用者分享：
        
      - Teams 部落格 (2020 年 2 月 28 日)：[使用 Microsoft Teams 在家工作的 4 個秘訣](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083)

      - [使用 Office 365 共同作業](https://support.office.com/article/Collaborate-with-Office-365-ac05a41e-0b49-4420-9ebc-190ee4e744f4)

      - [使用 Teams 和 Office 365 遠端工作](https://support.microsoft.com/help/4549995/working-remotely-with-teams-and-office-365)

3.  鼓勵每個人[安裝](get-clients.md#mobile-clients)並使用行動裝置應用程式：[iOS](https://go.microsoft.com/fwlink/?LinkId=835758)   [Android](https://go.microsoft.com/fwlink/p/?linkid=2102168)

    > [!NOTE]
    > 如果您位於中國，請前往這裡，以[在中國取得 Android 版 Teams](get-teams-android-in-china.md)

4.  設置[技術服務人員](troubleshoot-installation.md)，處理使用者查詢。


## <a name="communications"></a>通訊

使用 Teams 與員工保持連絡：
- [整個組織的 Teams](create-an-org-wide-team.md) 和[公司 Communicator](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator) 應用程式範本
    
- 傳送有關組織的在家工作以及健康和安全原則資訊。
    
- 在全公司的會議與拓展中使用[即時活動](teams-live-events/what-are-teams-live-events.md)。 如果您的會議有超過 250 個參與者，請將它設為即時活動。 

## <a name="personal-considerations"></a>個人考量

以下是您在成功在家工作的一些秘訣：

- 備妥限定的實際工作空間，光線良好且適當的人體工學設備。

- 對於工作時間和承諾有清楚的界定，並使用 Teams [目前狀態](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e)來指出在您目前不在。

- 特意在您的在家工作辦公室往返「通勤」；而不要把在家工作變成家裡等於工作。

- 定期站起來並休息。 散步、伸展，幫自己泡杯茶。

## <a name="known-issue-dialing-into-skype-for-business-or-teams-conference-ids"></a>已知問題：撥入商務用 Skype 或 Teams 會議識別碼

以下是 2020 年 2 月 7 日訊息中心文章 (MC203397) 的摘要：

Microsoft 知道，中國地區的部分使用者在撥入商務用 Skype 或 Teams 會議識別碼時發生問題。 在多數情況下，這些問題在於我們無法控制的外部系統。 問題往往在於當地行動電話和電話語音的通信業者。 

如果您遇到音訊會議問題，建議您執行下列動作：

- 要求來電者或會議召集人撥打電話給您的 PSTN 或行動電話號碼
- 從桌面或行動裝置用戶端透過 VoIP 加入通話或會議

如果您需要記錄支援票證，請包含下列項目：
    
- 實際通話時間
- 撥入的會議橋接器號碼
- 來電者電話網路
- 來電者電話號碼
