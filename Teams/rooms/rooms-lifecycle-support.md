---
title: 版本支援
ms.author: v-lanac
author: lanachin
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
description: 瞭解 Microsoft 團隊聊天室的生命週期支援，包括動態支援結構及其階段。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17e1dcd3c473b31754ac29d98db04747798d581f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650916"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft 團隊聊天室 app 版本支援
 
Microsoft 團隊聊天室 app 每年都會更新幾次。 每個支援 12 (12) 個月的更新 (GA) 發行日期。 提供的技術支援是整個 12 (12) 個月。 不過，支援結構是動態的，有兩個不同的階段（視最新版本的可用性而定）：

- **服務與重要更新階段** \- 當您執行最新版本的 Microsoft 團隊聊天室 app 時，您會收到包含 *安全性與服務* 更新的定期更新。

- **僅限安全更新階段** \- 當新版本的 Microsoft 團隊聊天室 app 發行時，較舊版本的應用程式的支援層級會降低，且 *僅* 適用于 12 (12) 個月生命週期中的其他部分。

> [!NOTE]
> 最新版本總是在 [服務] 和 [重要更新] 階段中。 當您遇到可保證重要更新的程式碼缺陷時，您也必須安裝最新的版本才能接收修正程式。 所有其他支援的版本只會有資格接收安全性更新。

所有的支援都是在某個版本的 12 (12) 月生命週期之後，或是自那時之後發行過多個更新時結束。 然後，客戶必須更新為支援的版本。

所有發行資訊都列在 [Microsoft 團隊聊天室版本](rooms-release-note.md)資訊中。

## <a name="windows-10-release-support"></a>Windows 10 版本支援

Microsoft 團隊聊天室需要 Windows 10 IoT Enterprise 或 Windows 10 Enterprise Sku，且位於 [Semi-Annual 通道服務選項] 底下。 不支援其他這些 Windows 10 版本：

- Windows 10 企業長期服務分支 (LTSB) /長期服務通道 (LTSC) 版本
- Windows 10 (IoT) Enterprise LTSB/LTSC 版本的網際網路
- windows 10 專業版或家用版等任何其他版本的 Windows

未立即在 Microsoft 團隊聊天室裝置上提供或更新 Windows 10 功能更新。 在 [Windows 10 發行資訊](https://docs.microsoft.com/windows/release-information/) 頁面上發佈之一般發行日期之後的六個月延遲。 延遲時間是用來驗證 Microsoft 團隊聊天室應用程式、裝置硬體及經過驗證的音訊視頻外設的 Windows 10 發行相容性。 驗證會在每個 Windows 10 主要版本的有效開發期間開始並繼續進行。 需要額外的時間來驗證所有裝置製造商是否已針對其裝置建立更新過的影像，以及 Microsoft 小組驗證並測試這些影像。 在驗證期間，Microsoft 團隊聊天室應用程式會使用  [商務用 Windows 更新群組原則](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 來延遲 Windows 10 功能更新。 發現並解決任何相容性問題之後，請透過 Windows 市集中新的 app 版本來更新群組原則，以提升封鎖。 在夜間維護重新開機期間，執行 Microsoft [團隊聊天室] app 的裝置會自動更新為適當的 Windows 10 版本。 您可以將 MSI 版本提供給想要手動管理更新的客戶。  

> [!IMPORTANT]
> 在驗證期間內，Microsoft 團隊機房裝置 **不** 應以任何方式更新到下一次發行的 Windows 10。 這包括覆蓋群群組原則，或使用 System Center 或其他協力廠商裝置管理服務。 上述任何情況都可能導致 Microsoft 團隊聊天室應用程式發生問題，或可能讓裝置無法使用。  

下表顯示已驗證支援 Microsoft 團隊聊天室的 Windows 10 版建議和支援版本。 所有日期都是以 ISO 8601 格式列出： YYYY MM。

|版本  |可用性日期   |Microsoft 團隊聊天室支援狀態   |Microsoft 團隊會議室的最小應用程式版本 | 建議的作業系統組建  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |在 [驗證] 底下， <br/>尚不支援|&#x2014; |19042.572 |
| 2004 |2020-05-27 |略過 <br/> 不建議使用|&#x2014; |19041.264 |
| 1909 |2019-11-12 |受 <br/>採用 |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |受  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |不支援， <br/>已知相容性問題 &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |不支援                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |不支援                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |不支援                         |&#x2014; |&#x2014; |

由於在 Microsoft 團隊聊天室應用程式中發現相容性問題，因此建議您 &#x2780; Windows 10 版本1809。 此特定問題會導致在夜間重新開機後，Microsoft 團隊聊天室應用程式無法啟動。 此問題已在 Windows 10 版本1903中解決。  

由於在 Microsoft 團隊聊天室應用程式中發現相容性問題，因此建議您 &#x2781; Windows 10 版本2004。 此特定問題會導致在夜間重新開機後，Microsoft 團隊聊天室應用程式無法啟動。 

當您使用受支援版本的 Windows 10 時，您將永遠會取得 Microsoft 團隊聊天室 app 的最新應用程式更新。  

## <a name="related-topics"></a>相關主題

[Microsoft 團隊聊天室說明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft 團隊聊天室版本資訊](rooms-release-note.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
