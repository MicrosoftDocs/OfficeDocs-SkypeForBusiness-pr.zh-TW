---
title: 直接路由 SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 深入瞭解直接路由，例如設定、必要的核心部署決定，以及語音路由考慮。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9e64dc908bafdd63b17e22716e76c4f04df1409
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588595"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a>Survivable 分支裝置 (SBA) 以進行直接路由-公開預覽


> [!NOTE]
> 這是公開預覽版本。

有時候，使用直接路由來連線到 Microsoft Phone 系統的客戶網站，可能會遇到網際網路中斷的問題。

假設客戶網站（稱為分支）暫時無法透過直接路由連線到 Microsoft 雲端。 不過，分支內的內部網路仍能完全運作，且使用者可以連線至提供 PSTN 連線的 (SBC) 的會話邊界控制器。

本文說明如何使用 Survivable 分支裝置 (SBA) 來啟用 Microsoft 手機系統，以便在發生中斷時，繼續撥打及接聽公用交換電話網絡 (PSTN) 呼叫。

## <a name="prerequisites"></a>必要條件

SBA 是由 Microsoft 提供給 SBC 供應商的可發佈程式碼，然後將程式碼內嵌在其 SBCs 的固件中。 

若要使用內嵌 Survivable 分支裝置取得最新的會話邊界控制器固件，請與您的 SBC 廠商聯繫。 此外，還需要下列專案：

- SBC 必須針對媒體旁路進行設定，以確保分支網站中的 Microsoft 團隊用戶端可以直接與 SBC 產生媒體的資料流程。 

- 應該在 SBA VM 作業系統上啟用 TLS 1.2。

## <a name="supported-teams-clients"></a>支援的團隊用戶端

下列 Microsoft 團隊用戶端支援 SBA 功能： 

- Microsoft 團隊 Windows 桌上出版 

- Microsoft 團隊 macOS 桌上出版 

## <a name="how-it-works"></a>運作方式

在網際網路停機期間，小組用戶端應該自動切換到 SBA，而進行中的通話應該會繼續不會中斷。 使用者不需要執行任何動作。 一旦團隊用戶端偵測到網際網路已啟動，而且所有撥出通話都已完成，用戶端就會回到正常操作模式並聯機至其他團隊服務。 SBA 會將收集的呼叫資料記錄上傳到雲端，通話記錄將會更新，以便由租使用者系統管理員來審查此資訊。 

當 Microsoft 團隊用戶端處於離線模式時，會提供下列與呼叫相關的功能： 

- 透過由 local SBA/SBC 進行 PSTN 呼叫，媒體會流過 SBC 進行。

- 透過由 local SBA/SBC 接收 PSTN 呼叫，且媒體流經 SBC。 

- 保留並繼續進行 PSTN 通話。

## <a name="configuration"></a>Configuration

為了讓 SBA 功能能夠運作，小組用戶端必須知道每個分支網站都提供哪些 SBAs，以及哪些 SBAs 指派給該網站中的使用者。 配置步驟如下所示：

1. 建立 SBAs。
2. 建立小組分支留存原則原則。
3. 指派原則給使用者。
4. 向 Azure Active Directory 註冊 SBA 應用程式。

所有設定都是使用商務用 Skype Online PowerShell Cmdlet 來完成。  (團隊系統管理中心還不支援直接路由 SBA 功能。 )  

 (如需有關設定 SBC 的資訊，以及 SBC 供應商檔的連結，請參閱本文結尾的會話邊界控制器設定。 ) 

### <a name="create-the-sbas"></a>建立 SBAs

若要建立 SBAs，您將會使用 New-CsTeamsSurvivableBranchAppliance Cmdlet。 這個 Cmdlet 具有下列參數：

| 參數| 說明 |
| :------------|:-------|
| Identity  | SBA 的 FQDN  |
| Fqdn | SBA 的 FQDN |
| 網站 | SBA 所在位置的 TenantNetworkSite |
| 描述 | 自由格式文字 |
|||

例如：

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.dk -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>建立小組分支留存原則 

若要建立原則，您可以使用 New-CsTeamsSurvivableBranchAppliancePolicy Cmdlet。 這個 Cmdlet 具有下列參數。 請注意，原則可以包含一或多個 SBAs。

| 參數| 說明 |
| :------------|:-------|
| Identity | 原則的身分識別 |
| BranchApplianceFqdns  | 網站中的 SBA (s) 的 FQDN |
||

例如：

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.dk, sba2.contoso.com} 
```

您可以使用 Set-CsTeamsSurvivableBranchAppliancePolicy Cmdlet，在原則中新增或移除 SBAs。 例如： 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>指派原則給使用者

若要將原則指派給個別的使用者，您將會使用 Grant-CsTeamsSurvivableBranchAppliancePolicy Cmdlet。 這個 Cmdlet 具有下列參數：

| 參數| 說明 |
| :------------|:-------|
| Identity | 使用者的身分識別 |
| PolicyName | 原則的身分識別 |
||

例如：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

您可以授與使用者的原則，方法是授予 $Null 原則，如下一個範例所示：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>使用 Azure Active Directory 註冊 SBA 應用程式

若要允許您租使用者中使用的不同 SBAs 從 Microsoft 365 讀取所需的資料，您必須使用 Azure Active Directory 註冊 SBA 的應用程式。 

如需應用程式註冊的詳細資訊，請參閱下列內容：

- [開發適用于 Azure Active Directory 的商務用電話應用程式](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [使用 Microsoft 身分識別平臺註冊應用程式](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。  

您只需要註冊一個應用程式，以供您租使用者中的所有 SBAs 使用。 

針對 SBA 註冊，您需要註冊所建立的下列值： 

- 應用程式 (用戶端) 識別碼 
- 用戶端密碼 

針對 SBA 應用程式，請記住下列事項： 

- 名稱可以是您決定的任何一種。  
- 受支援的帳戶類型 = 僅限此組織目錄中的帳戶。 
- 網頁重新導向 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient 。
- 隱含授與權杖 = 存取權杖和識別碼權杖。 
- API 許可權 = Skype 與團隊租使用者管理員存取-> 應用程式許可權-> application_access_custom_sba_appliance。
- 用戶端密碼：您可以使用任何描述和到期日。 
- 請記得在建立用戶端密碼之後，立即進行複製。 
- [概覽] 索引標籤上會顯示 (用戶端) 識別碼的應用程式。

然後按照下列步驟進行：

1. 註冊應用程式。
2. 設定隱式授與權杖。
3. 設定 API 許可權。
4. 建立用戶端密碼。


## <a name="session-border-controller-configuration"></a>會話邊界控制器配置 

如需如何使用內嵌 Survivable 分支裝置設定會話邊界控制器的逐步指導方針，請參閱您的 SBC 轉銷商提供的檔： 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [敷設](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [聯手](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-系統](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>報告問題

向您的 SBC 供應商支援組織報告任何問題。 報告問題時，請指出您有已設定的 Survivable 分支裝置。

## <a name="known-issues"></a>已知問題

- 當您新增 Survivable 分支裝置時，可能需要一些時間，才能在 Survivable 分支裝置原則中使用它們。

- 當您將 Survivable 分支裝置原則指派給使用者時，可能需要一段時間，才能讓 SBA 顯示在 CsOnlineUser 的輸出中。 

- 不會執行針對 Azure AD 連絡人的反向數位查閱。 

- SBA 不支援來電轉接設定。 

- 不支援針對動態緊急呼叫 (E911) 進行緊急呼叫設定。

- Get-CsOnlineUser 的輸出顯示 TeamsBranchSurvivabilityPolicy。
