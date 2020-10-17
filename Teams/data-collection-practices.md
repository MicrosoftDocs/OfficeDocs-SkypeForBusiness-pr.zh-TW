---
title: 資料收集做法
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: 瞭解 Microsoft 如何收集人口普查、使用量和錯誤資料，以瞭解 Teams 和商務用 Skype 的使用情況和問題，以便計畫產品改進。
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651224"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>商務用 Skype 和 Microsoft Teams 資料收集做法

商務用 Skype Server 和商務用 Skype Online 以及商務用 Skype 和 Microsoft Teams 應用程式收集資料，説明 Microsoft 瞭解這些產品的使用方式以及發生了哪些類型的錯誤，例如登入錯誤。 此資訊可協助我們瞭解使用模式、計畫新功能，以及疑難排解和解決問題區域。

雖然某些使用量資料是自動收集的，但其他資料只能在管理員和/或使用者選擇允許時收集。 資料收集分為以下三類：

- 人口普查資料

- 使用量資料

- 錯誤報告資料

## <a name="census-data"></a>人口普查資料

獲取人口普查資料完全是為了提供、支援和改進商務用 Skype。 Microsoft Teams 和商務用 Skype Online。 它包括環境資訊，如裝置和作業系統版本，以及區域和語言設置。 它還包括用於登入嘗試和失敗的計數器。 以下是收集的人口普查資料的一些具體示例：

|**資料類型**|**示例**|**注釋**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |這個識別碼被散列兩次：一次在用戶端上，一次在遙測服務上。 散列可確保識別碼無法連結到特定使用者。  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |裝置識別碼是在裝置上隨機生成一次並發送到遙測服務的 GUID。  <br/> |

人口普查資料不包含任何標識你的組織或使用者的資訊。 有關詳細資訊，請參閱 [商務用 Skype 隱私權聲明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)。

人口普查資料在預設情況下處於開啟狀態，管理員或最終使用者無法將其關閉。

## <a name="usage-data"></a>使用量資料

使用量資料包括諸如呼叫次數、傳送或接收的 IM 數量、加入的會議數量、使用的功能的頻率以及穩定性問題等資訊。

使用量資料中可能包含標識你的組織的資訊，如 contoso.com。 以下是收集的使用量資料的一些具體示例：

|**資料類型**|**示例**|**注釋**|
|:-----|:-----|:-----|
|發送的即時訊息  <br/> |12  <br/> ||
|已接收即時訊息  <br/> |5  <br/> ||
|加入會議 (嘗試)  <br/> |5  <br/> ||
|加入會議 (成功)  <br/> |4  <br/> ||
|通話/會議紀要  <br/> |30 分鐘  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |這是在 Office 365 中註冊的組織的名稱，以明文形式傳輸，這意味著它沒有被模糊處理。  <br/> |

使用量資料不包含任何標識使用者的資訊。

預設情況下，使用量資料收集處於開啟狀態，但本地管理員可以使用商務用 Skype Server 上的 DisableAutomaticSendTracing 群組原則設定將其關閉。 關閉此設定將影響組織中的所有使用者。 有關詳細資訊，請參閱[設定用戶端載入原則](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)。

最終使用者無法啟用或停用使用量資料收集。

對於 Skype 會議應用程式和 Join Launcher 網頁，控制遙測的方法是通過以下原則：

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

此原則預設為 false，因此預設情況下遙測收集處於關閉狀態。 此設定為每個池，並控制將 Skype 會議應用程式連線至該伺服器上主持的會議的所有使用者。

## <a name="error-reporting-data"></a>錯誤報告資料

錯誤報告資料可包含有關性能和可靠性、裝置設定、網路連線品質、錯誤碼、錯誤記錄和例外的資訊。 以下是收集的錯誤報告資料的一些具體示例：

|**資料類型**|**示例**|**注釋**|
|:-----|:-----|:-----|
|訊息方向  <br/> |傳入  <br/> ||
|交談狀態  <br/> |空閒  <br/> ||
|交談執行緒識別碼  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|UserID  <br/> |amosmarble <br/> |識別碼以明文形式傳送，遙測服務在儲存它之前對其進行雜湊處理  <br/> |

錯誤報告資料還可能包含個人身份資訊，例如使用者的 IP 位址和工作階段初始通訊協定統一資源識別項 (SIP URI)。 有關所收集內容的詳細說明，請參閱 [商務用 Skype 隱私權聲明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)。

錯誤報告需要兩個事項：

- 在伺服器或租用戶系統管理中心中，DisableAutomaticSendTracing 群組原則設定設定為 False (這是預設狀態)。 有關詳細資訊，請參閱[設定用戶端載入原則](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)。
    
- 最終使用者從 Skype for Business 用戶端的 [一般] 索引標籤 (按一下齒輪圖示![代表齒輪的圖示](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)，然後 **[選項]** 對話方塊開啟並顯示 **[一般]** 索引標簽) 單獨選擇加入。
    
 
![[選項] 對話方塊中 [資料收集] 核取方塊的螢幕截圖](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
對於 Skype 會議應用，MeetingUxEnableTelemetry 還控制錯誤報告，不過對於 Windows 上當機，Watson 設定控制上傳當機資訊。 Skype 會議應用程式沒有您在 [桌面用戶端] 對話方塊中看到的使用者設定。

有關詳細資訊，請參閱 [在商務用 Skype 中設定一般選項](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)。

您可以參閱[為商務用 Skype Online 設定網路](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)以設定網路。

如果您在中國使用由世紀互聯運營的 Microsoft 365 或 Office 365，請參閱[為世紀互聯運營的商務用 Skype Online 設定網路](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)。

## <a name="related-topics"></a>相關主題
[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
