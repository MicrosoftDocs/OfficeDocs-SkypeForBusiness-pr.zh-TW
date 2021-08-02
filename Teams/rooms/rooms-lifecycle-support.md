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
localization_priority: Normal
description: 瞭解系統生命週期支援Microsoft Teams 會議室，包括動態支援結構及其階段。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c34f448eeaadbf946ab708378caa835a94836ccc
ms.sourcegitcommit: ad215c120d7e550a7aebf2e1bb620c69039e5d8d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/01/2021
ms.locfileid: "53679728"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams 會議室應用程式版本支援
 
應用程式Microsoft Teams 會議室應用程式每年會獲得數次更新。 自發行日期起， (12) 12 個月內支援每個更新 (GA) 更新。 在 12 個月內提供 12 個月的 (技術支援) 支援。 不過，支援結構是動態的，有兩個不同的階段，取決於最新版本的可用性：

- **維護與重要更新階段**- 當您執行最新版本的 Microsoft Teams 會議室 App 時，您會收到包含安全性與維護更新 *的定期更新*。

- 僅安全性 **更新階段**- 當 Microsoft Teams 會議室 App 新版本發行時，繼承應用程式的支援等級會降低，僅針對 (12 個月週期的其餘 1) 2 (安全性更新。 

> [!NOTE]
> 最新版本一直位於維護與重要更新階段。 當您遇到需要重大更新的程式碼瑕疵時，您也必須安裝最新版本，以接收修正程式。 所有其他支援的版本都只能收到安全性更新。

所有支援在版本 (12) 月週期到期，或自那之後發行超過兩個更新之後結束。 接著，客戶必須更新至支援的版本。

所有版本會列在 Microsoft Teams 會議室[資訊中](rooms-release-note.md)。

## <a name="windows-10-release-support"></a>Windows 10版本支援

Microsoft Teams 會議室通道維護選項Windows 10 IoT 企業版或Windows 10 企業版 SKUS Semi-Annual SKUS。 不支援Windows 10版本：

- Windows 10 企業版LTS) B 或 ltSB (/長期維護通道 (LTSC) 服務分支
- Windows 10IoT (Internet) Enterprise LTSB / LTSC 版本
- 任何其他版本的Windows，例如Windows 10 專業版家用版

系統Windows 10裝置上不會立即提供新功能Microsoft Teams 會議室新功能更新。 在發佈于發行資訊頁面上的一般發行日期之後，Windows 10延遲達[六](/windows/release-information/)個月。 延遲時間會用來驗證 Windows 10應用程式、裝置硬體Microsoft Teams 會議室認證音訊視訊外Microsoft Teams 會議室的發行相容性。 驗證會在每個主要版本開發期間開始並繼續Windows 10。 需要額外時間驗證所有裝置製造商都為裝置建立更新的影像，Microsoft Teams認證和測試這些影像。 在驗證期間，Microsoft Teams會議室應用程式會Windows[商務用](/windows/deployment/update/waas-manage-updates-wufb)更新群組原則來延遲Windows 10更新。 找到並解決任何相容性問題之後，封鎖會透過新版 App 在 Windows 中更新群組原則Windows解除。 執行此應用程式Microsoft Teams 會議室裝置會在Windows 10維護重新開機期間自動更新至適當的版本。 MSI 版本可供想要手動管理更新的客戶使用。  

> [!IMPORTANT]
> 在驗證期間，Microsoft Teams 會議室不得以任何方式將裝置更新至Windows 10版本。 這包括重寫就地的群組原則，或System Center或其他協力廠商裝置管理服務。 上述任何一個都可能會導致會議室應用程式Microsoft Teams問題，或可能導致裝置無法使用。  

下表顯示建議和支援的版本，Windows 10驗證支援Microsoft Teams 會議室。 所有日期均以 ISO 8601 格式列出：YYYY-MM-DD。

|版本  |可用性日期   |Microsoft Teams 會議室支援狀態   |Microsoft Teams 會議室最低應用程式版本 | 建議的作業系統建立  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |支援 <br/>建議|4.8.31.0 |19042.631 |
| 2004 |2020-05-27 |跳 <br/> 不建議&#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |支援 |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |不支援  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |不支援， <br/>已知相容性問題&#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |不支援                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |不支援                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |不支援                         |&#x2014; |&#x2014; |

&#x2780; Windows 10應用程式發現相容性問題，不建議使用版本 2004 Microsoft Teams 會議室版本。 此特定問題Microsoft Teams 會議室重新開機之後，應用程式無法啟動。 

&#x2781; Windows 10版本 1809，因為發現應用程式相容性問題，不建議Microsoft Teams 會議室版本。 此特定問題Microsoft Teams 會議室重新開機之後，應用程式無法啟動。 此問題在版本 1903 Windows 10中已解決。  

當您使用支援的 Windows 10版本時，您一定會取得應用程式應用程式Microsoft Teams 會議室更新。  

> [!IMPORTANT]
> 由於Windows 10問題，下列裝置Teams 會議室 20H2 更新。 裝置 OEM 正在努力儘快解決這些問題。 Windows 10裝置上不會提供 20H2。 請勿將群群組原則物件 (GPO) MDM 管理 () 更新至 20H2。 
> 
> 有 compatiablity 問題的裝置有：
> 
> - Cresron UC-Engine (BIOS 版本/date 包含「KYSKLI」-表示「頭骨峽谷BIOS」)  

## <a name="related-topics"></a>相關主題

[Microsoft Teams 會議室協助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 會議室發行資訊](rooms-release-note.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
