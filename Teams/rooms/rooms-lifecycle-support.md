---
title: Microsoft Teams 會議室應用程式版本支援
ms.author: czawideh
author: cazawideh
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
description: 瞭解Microsoft Teams 會議室的生命週期支援，包括動態支援結構及其階段。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0353dc1a52dbc16d42d7c7e2f974675bb5098aa
ms.sourcegitcommit: cd4464fe9bf0f38ed4c3ca058a51bcd29578eef9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2022
ms.locfileid: "65316509"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams 會議室應用程式版本支援
 
Microsoft Teams 會議室應用程式會透過 Windows Store 取得更新。 Microsoft Teams Room 應用程式會使用持續更新的產品生命週期，且在任何指定時間只支援目前和下一個最新版本的應用程式。 Microsoft Teams會議室應用程式會搭售針對會議室使用而修改的Teams桌面應用程式的特定版本。 Teams桌面應用程式每兩周更新一次。 深入瞭解[Teams更新程式](../teams-client-update.md)。 這表示Teams 會議室應用程式目前-1 版最多可有 6 個Teams傳統型應用程式更新，因此建議您隨時將Teams Room 應用程式更新為最新版本的 Teams 會議室 應用程式。 

Teams 會議室的支援結構是動態的，取決於最新版本的可用性。 當您在非最新版本的應用程式中遇到程式碼瑕疵時，您必須安裝最新版本才能收到修正程式。

所有版本都會列在[Microsoft Teams 會議室版本資訊中](rooms-release-note.md)。

> [!IMPORTANT]
> 安裝舊版 Teams 會議室應用程式隨附的新裝置時，建議您在設定帳戶後[手動更新應用程式](manual-update.md)，然後再下載任何Windows更新。 這可確保您的裝置上已安裝正確的作業系統版本和Windows更新。  

## <a name="windows-10-release-support"></a>Windows 10發行支援

Microsoft Teams 會議室需要Semi-Annual通道服務選項底下的Windows 10 IoT 企業版或Windows 10 企業版 SKU。 不支援這些其他Windows 10版本：

- Windows 10 企業版長期維護分支 (LTSB) / 長期維護通道 (LTSC) 版本
- Windows 10物連線 (IoT) Enterprise LTSB / LTSC 版本
- 任何其他版本的 Windows，例如 Windows 10 專業版 版或家用版

Windows 10裝置上未立即提供新的 Microsoft Teams 會議室Windows 10功能更新。 在Windows 10[發行資訊](/windows/release-information/)頁面上發佈一般可用性日期之後，最多會有六個月或更久的刻意延遲。 這一次是用來驗證Microsoft Teams 會議室應用程式、裝置硬體和認證音訊視訊周邊裝置的Windows 10發行相容性。 驗證會在每個Windows 10主要版本的主動開發期間開始並繼續進行。 驗證所有裝置製造商都已為其裝置建置更新的影像，以及 Microsoft 認證和測試這些影像，需要額外的時間。 在驗證期間，Microsoft Teams Room 應用程式會使用[商務Windows Update組原則](/windows/deployment/update/waas-manage-updates-wufb)來延遲功能更新Windows 10。 找到並解決任何相容性問題之後，封鎖會透過Windows市集中的新應用程式發行來更新群組原則來解除封鎖。 執行 Microsoft Teams 會議室 應用程式的裝置會在夜間維護重新開機期間自動更新為適當的Windows 10版本。 MSI 版本可供需要手動管理更新的客戶使用。  

> [!IMPORTANT]
> 在驗證期間，Microsoft Teams 會議室裝置 **不應** 以任何方式更新至下一個Windows 10版本。 這包括覆寫就地的群組原則，或使用System Center或其他協力廠商裝置管理服務。 其中任何一項都可能會對 Microsoft Teams Room 應用程式造成問題，或讓裝置無法使用。  

下表顯示經驗證以支援Microsoft Teams 會議室的建議及支援的Windows 10版本。 所有日期都以 ISO 8601 格式列出：YYYY-MM-DD。

| 版本 | 可用日期 | Microsoft Teams 會議室支援狀態                    | Microsoft Teams 會議室最低應用程式版本 | 建議的作業系統組建 |
|:--------|:------------------|:--------------------------------------------------------|:--------------------------------------------------|:---------------------|
| 21H2    | 2021-11-16        | 支援<br>建議                               | 4.12.126.0                                        | 19044.1288           |
| 21H1    | 2021-05-18        | 不支援                                           | &#x2014;                                          | &#x2014;             |
| 20H2    | 2020-10-20        | 支援                                               | 4.10.10.0                                         | 19042.631            |
| 2004    | 2020-05-27        | 跳 <br/> 不建議&#x2780;                 | &#x2014;                                          | &#x2014;             |
| 1909    | 2019-11-12        | 支援                                               | 4.5.33.0                                          | 18363.418            |
| 1903    | 2019-05-21        | 不支援                                           | &#x2014;                                          | &#x2014;             |
| 1809    | 2019-03-28        | 不支援， <br/>已知的相容性問題&#x2781; | &#x2014;                                          | &#x2014;             |
| 1803    | 2018-07-10        | 不支援                                           | &#x2014;                                          | &#x2014;             |
| 1709    | 2018-01-18        | 不支援                                           | &#x2014;                                          | &#x2014;             |
| 1703    | 2017-07-11        | 不支援                                           | &#x2014;                                          | &#x2014;             |

由於Microsoft Teams 會議室應用程式的相容性問題，不建議&#x2780; Windows 10版本 2004。 此特定問題會導致Microsoft Teams 會議室應用程式在夜間重新開機後無法啟動。 

&#x2781; Windows 10版本 1809 不建議使用，因為Microsoft Teams 會議室應用程式有相容性問題。 此特定問題會導致Microsoft Teams 會議室應用程式在夜間重新開機後無法啟動。 此問題已在 Windows 10 版本 1903 中解決。  

當您使用支援的 Windows 10 版本時，您永遠會取得Microsoft Teams 會議室應用程式的最新應用程式更新。  


## <a name="related-topics"></a>相關主題

[Microsoft Teams 會議室說明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams 會議室版本資訊](rooms-release-note.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
