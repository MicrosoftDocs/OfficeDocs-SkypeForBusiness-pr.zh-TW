---
title: Microsoft Teams 會議室應用程式版本支援
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
ms.localizationpriority: medium
description: 瞭解系統生命週期支援Microsoft Teams 會議室，包括動態支援結構及其階段。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7e7a82d7643a925d5c997c9d6fe5661a421d47ab
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356421"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams 會議室應用程式版本支援
 
應用程式Microsoft Teams 會議室每季透過市/市Windows更新。 您可以在兩者之間進行帶外更新，以修正緊急問題。 Microsoft Teams會議室應用程式會使用常綠產品生命週期，且任何時間僅支援目前和最後一個版本的應用程式。 Microsoft Teams會議室應用程式會提供經過修改供會議室Teams版桌面應用程式的特定版本。 桌面Teams應用程式每兩周更新一次。 深入瞭解更新Teams[程式](../teams-client-update.md)。 這表示Teams 會議室應用程式目前-1 版本最多可以支援六個 Teams 桌面應用程式更新，因此建議您隨時將 Teams 會議室應用程式更新至 Teams 會議室 App 的最新版本。 

系統支援結構Teams 會議室動態，且取決於最新版本的可用性。 當您在不是最新版本的應用程式版本中遇到程式碼瑕疵時，您必須安裝最新版本，以接收修正程式。

所有版本都列在 Microsoft Teams 會議室[資訊中](rooms-release-note.md)。

> [!IMPORTANT]
> 安裝舊版 Teams 會議室應用程式所提供的新裝置時，建議您在設定帳戶之後手動更新應用程式，然後再下載任何[](manual-update.md)Windows更新。 這可確保您的裝置上安裝 correbt OS 版本和更新。  

## <a name="windows-10-release-support"></a>Windows 10版本支援

Microsoft Teams 會議室通道維護選項Windows 10 IoT 企業版或Windows 10 企業版 SKUS Semi-Annual SKUS。 不支援Windows 10版本：

- Windows 10 企業版LTSB (/長期維護通道) LTSC 版本 (服務分支) 服務分支
- Windows 10IoT (Internet) Enterprise LTSB / LTSC 版本
- 任何其他版本的Windows，例如Windows 10 專業版家用版

Windows 10裝置上不會立即提供新功能Microsoft Teams 會議室更新。 在發佈于發行資訊頁面上的一般發行日期之後，Windows 10[延遲達六個月以上](/windows/release-information/)。 這次用於驗證 Windows 10應用程式、Microsoft Teams 會議室硬體和認證音訊視訊周邊裝置版本相容性。 驗證會在每個主要版本開發期間開始並繼續Windows 10。 需要額外時間驗證所有裝置製造商已針對其裝置建立更新的影像，Microsoft Teams認證及測試這些影像。 在驗證期間，Microsoft Teams會議室應用程式會Windows[商務用](/windows/deployment/update/waas-manage-updates-wufb)更新群群組原則來延遲Windows 10更新。 找到並解決任何相容性問題之後，封鎖會透過在市/市中的新應用程式發行更新群組Windows解除。 執行此應用程式Microsoft Teams 會議室裝置會在Windows 10維護重新開機期間自動更新至適當的版本。 MSI 版本可供想要手動管理更新的客戶使用。  

> [!IMPORTANT]
> 在驗證期間，Microsoft Teams 會議室不得以任何方式將裝置更新至Windows 10版本。 這包括重寫就地的群組原則，或System Center或其他協力廠商裝置管理服務。 上述任何一個都可能會導致會議室應用程式Microsoft Teams問題，或讓裝置無法使用。  

下表顯示建議和支援的版本，Windows 10驗證支援Microsoft Teams 會議室。 所有日期均以 ISO 8601 格式列出：YYYY-MM-DD。

|版本  |可用性日期   |Microsoft Teams 會議室支援狀態   |Microsoft Teams 會議室最低應用程式版本 | 建議的作業系統建立  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |支援 <br/>建議|4.10.10.0 |19042.631 |
| 2004 |2020-05-27 |跳 <br/> 不建議&#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |支援 |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |不支援  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |不支援， <br/>已知相容性問題&#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |不支援                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |不支援                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |不支援                         |&#x2014; |&#x2014; |

&#x2780; Windows 10應用程式相容性問題，不建議使用版本 2004 Microsoft Teams 會議室版本。 此特定問題Microsoft Teams 會議室重新開機之後，應用程式無法啟動。 

&#x2781; Windows 10版本 1809，因為發現應用程式相容性問題，不建議Microsoft Teams 會議室版本。 此特定問題Microsoft Teams 會議室重新開機之後，應用程式無法啟動。 此問題在版本 1903 Windows 10中已解決。  

當您使用支援的 Windows 10版本時，您一定會取得應用程式應用程式Microsoft Teams 會議室更新。  


## <a name="related-topics"></a>相關主題

[Microsoft Teams 會議室協助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 會議室發行資訊](rooms-release-note.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
