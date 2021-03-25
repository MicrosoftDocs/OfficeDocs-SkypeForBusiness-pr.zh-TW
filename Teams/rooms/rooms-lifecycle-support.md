---
title: 版本支援
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 瞭解 Microsoft Teams 會議室的生命週期支援，包括動態支援結構及其階段。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e22bf9759920a5b4233fab9a6f6169f3a1153f0d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117441"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams 會議室應用程式版本支援
 
Microsoft Teams 會議室應用程式每年會獲得數次更新。 自發行日期起， (12) 12 個月支援每個更新 (GA) 更新。 在 12 個月內提供 12 個月 (技術支援) 支援。 不過，支援結構是動態的，有兩個不同的階段，取決於最新版本的可用性：

- **維護與重要更新階段** \- 當您執行最新版本的 Microsoft Teams 會議室應用程式時，您會收到包含安全性與維護更新 *的定期更新* 。

- **僅安全性更新階段** \-當新版本的 Microsoft Teams 會議室應用程式發行時，繼承應用程式的支援等級會降低，僅針對 12 個月週期的 12 (安全性更新) 更新。 

> [!NOTE]
> 最新版本一直位於維護與重要更新階段。 當您遇到需要重大更新的程式碼瑕疵時，您也必須安裝最新版本，以接收修正程式。 所有其他支援的版本都只能收到安全性更新。

所有支援在版本 (12) 月週期到期，或自那之後發行超過兩個更新之後結束。 接著，客戶必須更新至支援的版本。

所有版本都列在 Microsoft [Teams 會議室發行資訊中](rooms-release-note.md)。

## <a name="windows-10-release-support"></a>Windows 10 版本支援

Microsoft Teams 會議室需要 Windows 10 IoT 企業版或 Windows 10 企業版 SKUS Semi-Annual通道維護選項下。 不支援其他 Windows 10 版本：

- Windows 10 企業長期維護分支 (LTSB) / 長期維護通道 (LTSC) 版本
- Windows 10 企業版 LTSB (IoT) Internet / LTSC 版本
- 任何其他版本的 Windows，例如 Windows 10 專業版或家用版

Microsoft Teams 會議室裝置不會立即提供或更新 Windows 10 功能更新。 在 Windows [10](/windows/release-information/) 版本資訊頁面上發佈的一般可用性日期之後，故意延遲最多六個月。 延遲時間是用來驗證 Microsoft Teams 會議室應用程式、裝置硬體和認證音訊視訊周邊程式的 Windows 10 版本相容性。 在 Windows 10 的每個主要版本進行中開發期間，驗證會開始並繼續。 需要額外時間驗證所有裝置製造商已針對其裝置建立更新的影像，以及 Microsoft Teams 認證及測試這些影像。 在驗證期間，Microsoft Teams Room App 會使用  [商務用 Windows Update 群群組原則](/windows/deployment/update/waas-manage-updates-wufb) 來延遲 Windows 10 功能更新。 找到並解決任何相容性問題後，會透過 Windows 市面的新應用程式發行更新群組原則來解除封鎖。 執行 Microsoft Teams 會議室應用程式的裝置會在夜間維護重新開機期間自動更新至適當的 Windows 10 版本。 MSI 版本可供想要手動管理更新的客戶使用。  

> [!IMPORTANT]
> 在驗證期間，Microsoft Teams 會議室裝置不得以任何方式更新至 Windows 10 的下一版。 這包括重寫就地的群組原則，或是使用 System Center 或其他協力廠商裝置管理服務。 上述任何一種都可能會導致 Microsoft Teams Room 應用程式發生問題，或讓裝置無法使用。  

下表顯示經驗證支援 Microsoft Teams 會議室的 Windows 10 建議和支援版本。 所有日期均以 ISO 8601 格式列出：YYYY-MM-DD。

|版本  |可用性日期   |Microsoft Teams 會議室支援狀態   |Microsoft Teams 會議室最低應用程式版本 | 建議的作業系統建立  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |在驗證下， <br/>尚未支援|&#x2014; |19042.572 |
| 2004 |2020-05-27 |跳 <br/> 不建議使用|&#x2014; |19041.264 |
| 1909 |2019-11-12 |支援 <br/>推薦 |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |支援  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |不支援， <br/>已知相容性問題&#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |不支援                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |不支援                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |不支援                         |&#x2014; |&#x2014; |

&#x2780; Microsoft Teams 會議室應用程式發現相容性問題，不建議使用 Windows 10 版本 1809。 此特定問題會導致 Microsoft Teams 會議室應用程式在夜間重新開機後無法啟動。 此問題在 Windows 10 版本 1903 中已解決。  

&#x2781; Microsoft Teams 會議室應用程式發現相容性問題，不建議使用 Windows 10 版本 2004。 此特定問題會導致 Microsoft Teams 會議室應用程式在夜間重新開機後無法啟動。 

當您使用支援的 Windows 10 版本時，您一定會取得 Microsoft Teams 會議室應用程式的最新應用程式更新。  

## <a name="related-topics"></a>相關主題

[Microsoft Teams 會議室協助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 會議室版本資訊](rooms-release-note.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)