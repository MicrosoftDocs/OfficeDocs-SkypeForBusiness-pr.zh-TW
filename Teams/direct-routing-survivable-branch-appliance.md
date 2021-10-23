---
title: 直接路由 SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
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
description: 深入瞭解直接路由，例如組態、必要的核心部署決策，以及語音路由考慮。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c25299a0f0df6863bcb1fbaa4627b891a6e860a
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536754"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>適用于直接路由的 (分支裝置) SBA 裝置


有時候，使用直接路由連接到系統Microsoft 電話網站可能會遇到網際網路中斷。

假設客戶網站 ，稱為分支，暫時無法透過直接路由連接到 Microsoft 雲端。 不過，分支內的內部網路仍然功能完整，使用者可以連接到提供 PSTN (SBC) 會話邊界控制器。

本文說明如何使用可維護分支裝置 (SBA) ，讓 Microsoft 電話 系統在中斷時繼續撥打和接聽公用交換電話網路 (PSTN) 通話。

## <a name="prerequisites"></a>必要條件

SBA 是 Microsoft 提供給 SBC 廠商的可發佈程式碼，廠商接著將程式碼內嵌到其固件中，或將代碼分開發布，讓 SBA 在個別的虛擬機器或硬體上執行。 

若要使用內嵌的 Survivable 分支裝置取得最新的會話邊界控制器固件，請與您的 SBC 廠商聯繫。 此外，需要下列專案：

- SBC 必須針對媒體旁路進行配置，以確保分支Microsoft Teams用戶端中的媒體可以直接與 SBC 一起流動。 

- SBA VM OS 上應啟用 TLS1.2。
- Microsoft SBA Server 會使用埠 3443、4444 和 8443 與 Teams 用戶端通訊，而且應該允許使用防火牆。 
- Microsoft SBA Server (埠 5061 或 SBC) 上所配置的埠 5061，用於與 SBC 通訊，而且應該允許在防火牆上。 
- Microsoft SBA Server 會使用 UDP 埠 123 與 NTP 伺服器通訊，而且應該允許在防火牆上。
- Microsoft SBA Server 會使用埠 443 與 Microsoft 365通訊，而且應該允許在防火牆上。
- 應依照以下所述的指導方針定義公用雲端的 Azure IP 範圍和服務標記： https://www.microsoft.com/download/details.aspx?id=56519

## <a name="supported-teams-clients"></a>支援Teams用戶端

下列用戶端支援 SBA Microsoft Teams功能： 

- Microsoft Teams Windows桌面 

- Microsoft Teams macOS 桌上出版 

## <a name="how-it-works"></a>運作方式

在網際網路中斷期間，Teams用戶端應該會自動切換到 SBA，而持續通話應該不會中斷。 使用者不需要執行任何動作。 當用戶端Teams網際網路已上線且任何撥出通話完成時，用戶端就會回到正常作業模式，並連接到其他Teams服務。 SBA 會將收集的通話資料記錄上傳至雲端，通話記錄將會更新，以便租使用者系統管理員能夠查看此資訊。 

當Microsoft Teams用戶端處於離線模式時，可以使用下列與通話相關的功能： 

- 透過當地 SBA/SBC 撥打 PSTN 通話，媒體會透過 SBC 進行。

- 透過當地 SBA/SBC 接收 PSTN 通話，媒體會透過 SBC 進行。 

- 保留和繼續 PSTN 通話。

## <a name="configuration"></a>配置

若要讓 SBA 功能能夠Teams用戶端需要知道每個分支網站中可用的 SBA，以及指派給該網站中的使用者哪些 SBA。 組組步驟如下：

1. 建立 SBA。
2. 建立Teams可生存性政策。
3. 將策略指派給使用者。
4. 使用應用程式註冊 SBA Azure Active Directory。

所有組商務用 Skype線上 PowerShell Cmdlet 完成。  (系統Teams系統管理中心尚未支援直接路由 SBA 功能。)  

 (有關 SBC 的組建資訊，以及 SBC 廠商檔的連結，請參閱本文結尾的會話邊界控制器組) 

### <a name="create-the-sbas"></a>建立 SBA

若要建立 SBA，您將使用 New-CsTeamsSurvivableBranchAppliance Cmdlet。 此 Cmdlet 具有下列參數：

| 參數| 說明 |
| :------------|:-------|
| Identity  | SBA 的身分識別  |
| Fqdn | SBA 的 FQDN |
| 網站 | SBA 所在的 TenantNetworkSite |
| 描述 | 免費格式文字 |
|||

例如：

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>建立分支Teams性政策 

若要建立策略，請使用 New-CsTeamsSurvivableBranchAppliancePolicy Cmdlet。 此 Cmdlet 具有下列參數。 請注意，該策略可以包含一或多個 SBA。

| 參數| 說明 |
| :------------|:-------|
| Identity | 策略的身分識別 |
| BranchApplianceFqdns  | SBA 的 FQDN (網站) 的 FQDN |
||

例如：

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

您可以使用 Cmdlet 從策略新增或移除 SBA Set-CsTeamsSurvivableBranchAppliancePolicy。 例如： 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>指派策略給使用者

若要將策略指派給個別使用者，您將使用 Grant-CsTeamsSurvivableBranchAppliancePolicy Cmdlet。 此 Cmdlet 具有下列參數：

| 參數| 說明 |
| :------------|:-------|
| Identity | 使用者身分識別 |
| PolicyName | 策略的身分識別 |
||

例如：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

您可以像下一個範例所示，$Null使用者移除策略：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>使用應用程式註冊 SBA Azure Active Directory

若要允許租使用者內使用的不同 SBA 從 Microsoft 365 讀取必要的資料，您必須使用 Azure Active Directory 註冊 SBA 應用程式。 

有關應用程式註冊的資訊，請參閱下列專案：

- [開發商務用應用程式Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [使用 Microsoft 身分識別平臺](/azure/active-directory/develop/quickstart-register-app)註冊應用程式。  

您只需要註冊一個應用程式，才能由租使用者中所有的 SBA 使用。 

對於 SBA 註冊，您需要註冊所建立下列值： 

- 應用程式 (用戶端) 識別碼 
- 用戶端密碼 

針對 SBA 應用程式，請記住下列事項： 

- 名稱可以是您決定的任何專案。  
- 支援的帳戶類型 = 僅此組織目錄中的帳戶。 
- Web 重新導向 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient 。
- 隱含授權權杖 = Access 權杖和識別碼權杖。 
- API 許可權 = Skype及Teams租使用者系統管理員存取權 ->應用程式許可權 -> application_access_custom_sba_appliance。
- 用戶端金鑰：您可以使用任何描述和到期。 
- 請記得在建立用戶端密碼後立即複製。 
- 應用程式 (用戶端) 識別碼會顯示在概觀選項卡上。

然後按照下列步驟進行：

1. 註冊應用程式。
2. 設定隱含的授予權杖。
3. 設定 API 許可權。
4. 建立用戶端密碼。


## <a name="session-border-controller-configuration"></a>會話邊界控制器組 

若要瞭解如何使用內嵌的 Survivable 分支裝置設定會話邊界控制器的逐步指南，請參閱 SBC 廠商提供的檔： 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [功能區](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>報告問題

向 SBC 廠商的支援組織報告任何問題。 報告問題時，請指出您擁有已配置的 Survivable 分支裝置。

## <a name="known-issues"></a>已知問題

- 當您新增可替代的分支裝置時，可能需要一些時間，才能在可生存的分支裝置策略中使用它們。

- 當您將可維分支裝置策略指派給使用者時，可能需要一些時間，SBA 才能顯示在 Get-CsOnlineUser 的輸出中。 

- 不會針對連絡人Azure AD反向數位尋找。 

- SBA 不支援呼叫轉呼叫設定。 

- 不支援撥打 E911 (緊急) 緊急號碼。
