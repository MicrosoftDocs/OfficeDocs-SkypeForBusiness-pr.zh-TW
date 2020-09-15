---
title: 資料收集方式
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
description: 瞭解 Microsoft 如何收集人口普查、使用方式及錯誤資料，以瞭解團隊及商務用 Skype 使用方式及問題，以便規劃產品改良。
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651224"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>商務用 Skype 和 Microsoft 團隊資料收集做法

商務用 skype Server 及商務用 skype Online，以及商務用 Skype 和 Microsoft 團隊 app，收集資料以協助 Microsoft 瞭解這些產品的使用方式，以及發生的錯誤類型（例如登入錯誤）。 此資訊可協助我們瞭解使用模式、規劃新功能，以及疑難排解及修正問題區域。

當您自動收集一些使用資料時，只有當系統管理員和/或使用者選擇允許時，才能收集其他資料。 資料收集分為下列三種類別：

- 人口普查資料

- 使用量資料

- 錯誤報表資料

## <a name="census-data"></a>人口普查資料

人口普查資料是專為提供、支援及改善商務用 Skype 而取得的。 Microsoft 團隊及商務用 Skype Online。 它包含諸如裝置與作業系統版本等環境資訊，以及地區和語言設定。 它也包含登入嘗試與失敗的計數器。 以下是收集的統計資料的一些特定範例：

|**資料類型**|**範例**|**筆記**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |此識別碼的雜湊是兩次：一次在用戶端，然後再次在遙測服務。 雜湊確保 ID 無法連結至特定使用者。  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |裝置識別碼是一個 GUID，在裝置上隨機產生一次並傳送到遙測服務。  <br/> |

人口普查資料不包含任何可識別貴組織或使用者的資訊。 如需詳細資訊，請參閱 [商務用 Skype 隱私權聲明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) 。

人口統計資料預設為開啟，且無法由系統管理員或使用者關閉。

## <a name="usage-data"></a>使用量資料

使用方式資料包括諸如撥打數、送出或接收的 Im 數、已加入的會議數量、所使用的功能及穩定性問題等資訊。

使用狀況資料可能包含識別貴組織的資訊，例如 contoso.com。 以下是收集的用法資料的一些特定範例：

|**資料類型**|**範例**|**筆記**|
|:-----|:-----|:-----|
|傳送的 IM  <br/> |之間  <br/> ||
|已接收 IM  <br/> |500  <br/> ||
|加入會議 (嘗試)   <br/> |500  <br/> ||
|加入會議 (成功)   <br/> |4  <br/> ||
|通話/會議紀要  <br/> |30分鐘  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |這是在 Office 365 中註冊並以明文傳送的組織名稱，這表示它不會被混淆。  <br/> |

使用量資料不包含任何可識別使用者的資訊。

使用方式資料收集預設為開啟，但內部部署系統管理員可以使用商務用 Skype Server 上的 [DisableAutomaticSendTracing] 群組原則設定將它關閉。 關閉此設定會影響組織中的所有使用者。 如需詳細資訊，請參閱 [設定用戶端引導原則](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) 。

最終使用者無法開啟或關閉使用資料收集。

針對 Skype 會議應用程式和加入啟動器網頁，控制遙測的方式是透過此原則進行：

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

此原則預設為 false，因此預設會關閉遙測收集。 此設定為 [每個池]，並控制所有與 Skype 會議應用程式連線的使用者，以及在該伺服器上主持的會議。

## <a name="error-reporting-data"></a>錯誤報表資料

錯誤報表資料可包含有關效能、可靠性、裝置設定、網路連線品質、錯誤代碼、錯誤記錄和例外狀況的資訊。 以下是收集的錯誤報表資料的一些特定範例：

|**資料類型**|**範例**|**筆記**|
|:-----|:-----|:-----|
|訊息方向  <br/> |入帳  <br/> ||
|交談狀態  <br/> |超過  <br/> ||
|交談執行緒識別碼  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA = =  <br/> ||
|UserID  <br/> |amosmarble <br/> |識別碼是以明文傳送，在儲存前，遙測服務的雜湊值  <br/> |

錯誤報表資料也可能包含個人身分識別資訊，例如使用者的 IP 位址及會話初始通訊協定統一資源識別項 (SIP URI) 。 如需收集項目的詳細說明，請參閱 [商務用 Skype 隱私權聲明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) 。

錯誤報表需要兩個專案：

- [DisableAutomaticSendTracing] 群組原則設定在伺服器或 [租使用者系統管理中心] 中設定為 False (這是預設狀態) 。 如需詳細資訊，請參閱 [設定用戶端引導原則](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) 。
    
- 使用者在 [一般] 索引標籤中個別加入宣告， (按一下齒輪圖示 ![ 代表齒輪的圖示， ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) 然後 [ **選項** ] 對話方塊隨即開啟，並在商務用 Skype 用戶端中) 顯示 [ **一般** ] 索引標籤。
    
 
![[選項] 對話方塊中 [資料收集] 核取方塊的螢幕擷取畫面](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
若是 Skype 會議應用程式，MeetingUxEnableTelemetry 也會控制錯誤報表，但在 Windows 上，Watson 設定會控制上傳損毀資訊。 您可以在 [桌面用戶端] 對話方塊中看到 Skype 會議應用程式的使用者設定。

如需詳細資訊，請參閱 [設定商務用 Skype 中的一般選項](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) 。

您可以參閱為 [商務用 Skype Online 設定您的網路](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) ，以設定您的網路。

如果您使用的是中國由世紀運營的 Microsoft 365 或 Office 365，請參閱 [針對由世紀運營的商務用 Skype Online 設定您的網路](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)。

## <a name="related-topics"></a>相關主題
[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
