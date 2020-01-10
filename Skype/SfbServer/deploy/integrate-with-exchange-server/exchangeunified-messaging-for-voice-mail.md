---
title: 針對商務用 Skype Server 2015 語音信箱設定 Exchange Server 2013 整合通訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 摘要：針對商務用 Skype Server 語音信箱設定 Exchange Server 整合訊息。
ms.openlocfilehash: 61df3cb7f57a0fd924188f43374f0309d081b660
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001203"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>針對商務用 Skype Server 2015 語音信箱設定 Exchange Server 2013 整合通訊
 
**摘要：** 針對商務用 Skype Server 語音信箱設定 Exchange Server 整合訊息。
  
商務用 Skype Server 可讓您在 Exchange Server 2016 或 Exchange Server 2013 中儲存語音信箱訊息;這些語音信箱訊息就會以電子郵件訊息的方式顯示在使用者的收件匣中。 

> [!NOTE]
> Exchange 2019 中已不再提供 exchange 整合訊息（如前所述），但是您仍然可以使用電話系統來錄製語音信箱訊息，然後將錄製內容留在使用者的 Exchange 信箱中。 如需詳細資訊，請參閱[規劃雲端語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。
  
如果您已在商務用 Skype Server 與 Exchange Server 2016 或 Exchange server 2013 之間設定了伺服器對伺服器驗證，就表示您已準備好設定整合訊息。 若要這樣做，您必須先在 Exchange 伺服器上建立並指派新的統一訊息撥號方案。 例如，這兩個命令（從 Exchange 管理命令介面內部執行）會為 Exchange 設定新的3位數撥號方案：
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

在範例中的第一個命令中，VoIPSecurity 參數和參數值「受保護」，表示信號通道是使用傳輸層安全性（TLS）來加密。 URIType "SipName" 代表將使用 SIP 通訊協定來傳送和接收郵件，而 CountryOrRegionCode 1 則表示您的撥號計畫適用于美國。
  
在第二個命令中，傳遞給 ConfiguredInCountryOrRegionGroups 參數的參數值會指定可與此撥號方案搭配使用的國家/地區群組。 參數值 "隨處，\*"\*，\*"會設定下列專案：
  
- 組名（"隨處"）
    
- AllowedNumberString （\*，萬用字元代表允許的任何數位字串）
    
- DialNumberString （\*，代表允許任何撥入號碼的萬用字元）
    
- TextComment （\*，萬用字元代表允許使用任何文字命令）
    
> [!NOTE]
> 建立新的撥號方案也會建立預設信箱原則。 
  
建立及設定新的撥號方案之後，您必須將新的撥號方案新增至您的統一訊息伺服器，然後修改該伺服器的啟動模式。特別是，您必須將 [啟動模式] 設定為 "雙"。 您可以從 Exchange 管理命令介面內執行這兩項工作：
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

在已設定統一訊息伺服器之後，您必須接著執行 ExchangeCertificate Cmdlet，以確保您的 Exchange 憑證已套用到整合訊息服務：
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

在正確指派憑證之後，您必須停止並重新啟動統一訊息伺服器上的 MsExchangeUM 服務。 每當您變更啟動模式時，都必須停止並重新啟動此服務。
  
完成整合郵件伺服器的設定之後，您就可以設定 UM 呼叫路由器：
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

因為啟動模式已變更，所以您必須停止並重新啟動託管 UM 呼叫路由器的電腦上的 MsExchangeUMCR 服務。
  
若要完成統一訊息設定，您必須建立 UM 信箱原則，然後使用該原則來允許使用者使用整合訊息。 您可以使用類似以下的命令來建立信箱原則：
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

而且，您可以使用類似以下的命令，讓使用者能夠使用整合訊息：
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

在上述命令中，Extensions 參數代表使用者的電話分機號碼。 在這個範例中，使用者的分機號碼是100。
  
在您啟用自己的信箱之後，使用者 kenmyer@litwareinc.com 應該能夠使用 Exchange 整合訊息。 您可以從商務用 Skype Server Management Shell 中執行[Test CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) Cmdlet，以確認使用者可以連線到 Exchange UM：
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

如果您有另一個已啟用整合訊息的使用者，您可以使用[CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) Cmdlet，確認此第二位使用者可以為第一個使用者留下語音信箱訊息。
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>在 Microsoft Exchange Server 上設定整合通訊 
> [!IMPORTANT]
> 如果您想要使用 Exchange 整合訊息（UM）來提供呼叫應答、Outlook Voice Access 或適用于企業語音使用者的自動助理服務，請參閱[在商務用 Skype 中的 Exchange 整合訊息整合規劃](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)，然後依照本節中的指示進行。 

若要設定 Exchange 整合通訊（UM）以搭配企業語音使用，您必須執行下列工作：

- 在運行 Exchange 整合通訊（UM）服務的伺服器上設定憑證
  > [!NOTE]
  > 將所有用戶端存取和信箱伺服器新增到所有 UM SIP URI 撥號方案。 如果不是，傳出通話路由將無法如期運作。 
- 視需要建立一個或多個 UM SIP URI 撥號方案，以及訂閱者的存取電話號碼，然後建立對應的 L 撥號方案。

- 使用 exchucutil. ps1 腳本來：
    - 建立 UM IP 閘道。
    - 建立 UM 查尋群組。
    - [授與商務用 Skype 伺服器] 許可權以讀取 UM Active Directory 網域服務物件。
- 建立 UM 自動助理物件。
- 建立訂閱者存取物件。
- 為每位使用者建立 SIP URI，並將使用者與 UM SIP URI 撥號方案產生關聯。

### <a name="requirements-and-recommendations"></a>需求與建議

在開始之前，本節中的檔假設您已部署下列 Exchange 角色：用戶端存取和信箱。 在 Microsoft Exchange Server 中，Exchange UM 在這些伺服器上以服務的方式執行。

另請注意下列事項：
- 如果 Exchange UM 安裝在多個目錄林中，則必須針對每個 UM 林執行 Exchange Server 整合步驟。 此外，每個 UM 目錄林都必須設定為信任在其中部署商務用 Skype 伺服器的林，而商務用 whichSkype 中的林必須設定為信任每個 UM 目錄林。
- 整合步驟是在執行整合訊息服務的 Exchange 伺服器角色，以及在執行商務用 Skype Server 的伺服器上執行。 在執行 Lync Server 2013 整合步驟之前，您應該執行 Exchange Server 整合訊息整合的步驟。
  > [!NOTE]
  > 若要查看要對哪些伺服器以及哪些系統管理員角色執行哪些整合步驟，請參閱[整合內部部署整合訊息與商務用 Skype 的部署程式概覽](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)。 

在執行 Exchange UM 的每個伺服器上，都必須提供下列工具：
- Exchange 管理命令介面
- 腳本 exchucutil. ps1，可執行下列任務：
    - 針對每個商務用 Skype 伺服器建立 UM IP 閘道。
    - 為每個閘道建立一個 [查尋] 群組。 每個查尋群組的先導識別碼，會指定與閘道相關聯的前端池或標準版伺服器所使用的 UM SIP URI 撥號方案。
    - 在 Active Directory 網域服務中，授與商務用 Skype 伺服器的許可權，以讀取 Exchange UM 物件。



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>使用 ExchUCUtil 在 Microsoft Exchange 上設定整合通訊 

當您將 Microsoft 商務用 Skype Server 與 Exchange 整合通訊（UM）整合在一起，您必須在 Shell 中執行 ExchUcUtil 腳本。 ExchUcUtil. ps1 腳本會執行下列動作：

- 針對每個商務用 Skype 伺服器池建立 UM IP 閘道。

> [!IMPORTANT]
> ExchUcUtil. ps1 腳本會建立一個或多個 UM IP 閘道。 您必須在所有 UM IP 閘道上停用撥出電話，除了該腳本建立的一個閘道外。 這包括在執行腳本前，在已建立的 UM IP 閘道上停用撥出通話。 

- 針對每個 UM IP 閘道建立 UM 查尋群組。 每個查尋群組的試驗識別碼，會指定與 UM IP 閘道相關的商務用 Skype Server 前端池或標準版伺服器所使用的 UM SIP URI 撥號方案。
- 授與商務用 Skype 伺服器的許可權，以讀取 Active Directory UM 容器物件（例如 UM 撥號方案、自動語音應答、UM IP 閘道及 UM 查尋群組）。
  > [!IMPORTANT]
  > 每個 UM 林都必須設定為信任部署商務用 Skype Server 的林，以及部署商務用 Skype Server 2013 的林必須設定為信任每個 UM 目錄林。 如果 Exchange UM 是安裝在多個目錄林中，則必須針對每個 UM 林執行 Exchange Server integration 步驟，否則您必須指定商務用 Skype Server 網域。 例如，ExchUcUtil. ps1 –林： <lync-網域-控制器-fqdn>。 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>使用 Shell 執行 ExchUcUtil. ps1 腳本

在貴組織中的任何 Exchange 伺服器上執行 ExchUcUtil 腳本，這些伺服器與商務用 Skype Server 在相同的拓撲中。 您可以使用 Shell 從信箱伺服器執行腳本，或者您可以在用戶端存取伺服器上使用遠端 Windows PowerShell 來執行腳本。 如果您在組織中的用戶端存取伺服器上執行腳本，用戶端存取伺服器會將遠端 Windows PowerShell 會話 proxy 給組織中的信箱伺服器。
> [!IMPORTANT]
> ExchUcUtil. ps1 腳本會建立一個或多個 UM IP 閘道。 您必須在所有 UM IP 閘道上停用撥出電話，除了該腳本建立的一個閘道外。 這包括在執行腳本前，在已建立的 UM IP 閘道上停用撥出通話。 若要在 UM IP 閘道停用撥出電話，請參閱在 UM IP 閘道停用撥出電話。 
> [!IMPORTANT]
> 您必須具備 Exchange 組織管理角色的許可權，或是 Exchange 組織管理員安全性群組的成員，才能執行腳本。 

1. 開啟 Exchange 管理命令介面。
2. 在 C:\Windows\System32 提示字元中，**輸入\<cd drive 字母>： \Program Files\Microsoft\Exchange Server\V15\Scripts>。ExchUcUtil......**.... ps1，然後按 enter。

#### <a name="how-do-you-know-this-worked"></a>如何知道這是正常運作的？

若要確認 ExchUcUtul 腳本已順利完成，請執行下列動作：
- 使用 UMIPGateway Cmdlet 或 EAC 來查看已建立的新 UM IP 閘道或閘道。
- 使用 UMHuntGroup Cmdlet 或 EAC 來查看新的 UM 查尋群組或已建立的群組。

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>在運行 Exchange Server 整合通訊的伺服器上設定憑證
 
如果您已部署 Exchange 整合訊息（UM），請參閱規劃檔中的商務用 Skype Server 中的 Exchange 整合訊息整合規劃中所述，而且您想要在您的電腦中為企業語音使用者提供 Exchange UM 功能組織中，您可以使用下列程式來設定執行 Exchange UM 之伺服器上的憑證。

> [!IMPORTANT]
> 對於內部憑證，執行商務用 Skype 伺服器的伺服器以及執行 Microsoft Exchange 的伺服器，都必須有受信任的根授權憑證（相互信任）。 只要伺服器已在其受信任的根授權憑證存放區中註冊認證機構的根憑證，憑證授權單位（CA）就可以是相同或不同的憑證授權單位。 

Exchange 伺服器必須使用伺服器憑證進行設定，才能連線至商務用 Skype Server：
1. 下載 Exchange 伺服器的 CA 憑證。
2. 安裝 Exchange 伺服器的 CA 憑證。
3. 確認 CA 位於 Exchange 伺服器的根信任 Ca 清單中。
4. 建立 Exchange 伺服器的憑證要求並安裝證書。 
5. 指派 Exchange 伺服器的憑證。


**若要下載 CA 憑證：**

1. 在執行 Exchange UM 的伺服器上，按一下 [**開始**]，按一下 [**執行**]，輸入**您頒發 CA 伺服器的 HTTP://\<名稱>/certsrv**，然後按一下 **[確定]**。
2. 在 [選取任務] 底下，按一下 [**下載 CA 憑證、憑證鏈或 CRL**]。
3. 在 [**下載 Ca 憑證、憑證連結或 CRL**] 底下，選取 [**編碼方法至基本 64**]，然後按一下 [**下載 CA 憑證**]。
   > [!NOTE]
   > 您也可以在此步驟指定可分辨編碼規則（DER）編碼。 如果您選取 [DER 編碼]，此程式的下一個步驟中和**安裝 CA 憑證**的步驟10中的檔案類型是. p7b （而不是 .cer）。 
4. 在 [檔案**下載**] 對話方塊中，按一下 [**儲存**]，然後將檔案儲存到伺服器上的硬碟。 （根據您在上一個步驟中選取的編碼，該檔案將會有 .cer 或. p7b 檔案副檔名。）

**若要安裝 CA 憑證：**

1. 在執行 Exchange UM 的伺服器上，按一下 [**開始**]，按一下 [**執行**]，在 [開啟] 方塊中輸入**MMC** ，然後按一下 **[確定]**。
2. **在 [檔案**] 功能表上，按一下 [**新增/移除管理單元**]，然後按一下 [**新增**]。
3. 在 [**新增獨立的管理單元**] 方塊中，按一下 [**憑證**]，然後按一下 [**新增**]。
4. 在 [**憑證管理單元**] 對話方塊中，按一下 [**電腦帳戶**]，然後按一下 **[下一步]**。
5. 在 [**選取電腦**] 對話方塊中，確認已選取 [**本機電腦（執行此主控台的電腦）** ] 核取方塊，然後按一下 **[完成]**。
6. 按一下 [**關閉**]，然後按一下 **[確定]**。 
7. 在主控台樹中，展開 [**憑證（本機電腦）**]，展開 [**信任的根憑證授權單位**]，然後按一下 [**憑證**]。
8. 以滑鼠右鍵按一下 [**憑證**]，按一下 [**所有任務**]，然後按一下 [匯**入**]。
9. 按一下 **[下一步]**。 
10. 按一下 **[流覽]** 找出檔案，然後按一下 **[下一步**]。 （檔案將會有 .cer 或. p7b 副檔名，視您在**下載 CA 憑證**的步驟3中所選取的編碼而定。
11. 按一下 [**將所有憑證放**入下列存放區]。
12. 按一下 **[流覽]**，然後選取 [**信任的根憑證授權單位**]。 
13. 按一下 **[下一步**] 驗證設定，然後按一下 **[完成]**。 


**若要確認 CA 是否在受信任的根 Ca 清單中：**

1. 在執行 Exchange UM 的伺服器上，在 MMC 中展開 [憑證（本機電腦）]，展開 [信任的根憑證授權單位]，然後按一下 [憑證]。
2. 在 [詳細資料] 窗格中，確認您的 CA 位於信任的 Ca 清單中。


