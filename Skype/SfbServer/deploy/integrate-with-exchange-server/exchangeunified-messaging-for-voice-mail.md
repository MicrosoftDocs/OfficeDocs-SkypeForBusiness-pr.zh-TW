---
title: 設定商務用 Skype Server 語音信箱 Exchange Server 整合通訊
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 摘要：設定商務用 Skype Server 語音信箱 Exchange Server 整合通訊。
ms.openlocfilehash: e434309c67469ccaa6994ec90cb3431b9de4f13b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865280"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>設定商務用 Skype Server 語音信箱 Exchange Server 整合通訊
 
**摘要：** 設定商務用 Skype Server 語音信箱 Exchange Server 整合通訊。
  
商務用 Skype Server 可讓您將語音信箱訊息儲存在 Exchange Server 2016 或 Exchange Server 2013 中;這些語音信箱訊息會以電子郵件訊息的方式顯示在使用者的收件匣中。 

> [!NOTE]
> ExchangeExchange 2019 不再提供整合通訊，但您仍然可以使用電話系統來錄製語音信箱訊息，然後在使用者的 Exchange 信箱中留下記錄。 如需詳細資訊，請參閱[Plan 雲端語音信箱 service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 。
  
如果您已在商務用 Skype Server 和 Exchange Server 2016 或 Exchange Server 2013 之間設定伺服器對伺服器的驗證，就可以設定整合通訊。 若要這麼做，您必須先在您的 Exchange Server 上建立並指派新的整合通訊撥號對應表。 例如，在 Exchange 管理命令介面中 (執行這兩個命令，) 為 Exchange 設定新的3位數撥號對應表：
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

在範例中的第一個命令中，VoIPSecurity 參數和參數值「安全」表示使用傳輸層安全性 (TLS) 加密信號通道。 URIType "SipName" 指出會使用 SIP 通訊協定來傳送和接收訊息，而 CountryOrRegionCode 的 1 則指出撥號對應表是套用至美國。
  
在第二個命令中，傳送至 ConfiguredInCountryOrRegionGroups 參數的參數值指定了可使用此撥號對應表的的國內群組。 參數值 "Anywhere，， \* \* \* " 設定下列專案：
  
- 群組名稱 ("Anywhere")
    
- AllowedNumberString (\* ，表示允許任何數位字串的萬用字元) 
    
- DialNumberString (\* ，表示允許任何撥入號碼的通配字元) 
    
- TextComment (\* ，表示允許任何文字命令的萬用字元) 
    
> [!NOTE]
> 建立新的撥號對應表也會建立預設信箱原則。 
  
建立並設定新的撥號對應表之後，您必須將新的撥號對應表新增至整合通訊伺服器，然後修改該伺服器的啟動模式；明確地說，您必須將啟動模式設定為「雙重」模式。 您可以從 Exchange 管理命令介面內執行下列兩項工作：
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

設定整合通訊伺服器之後，您應該接下來執行 Enable-ExchangeCertificate Cmdlet，以確保將 Exchange 憑證套用至整合通訊服務：
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

正確指派憑證之後，您就必須停止並重新啟動整合通訊伺服器上的 MsExchangeUM 服務。每當您變更啟動模式時，都必須停止並重新啟動此服務。
  
完成整合通訊伺服器的設定之後，您就可以開始設定 UM 通話路由器：
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

由於啟動模式已變更，因此您必須停止並重新啟動主控 UM 通話路由器之電腦上的 MsExchangeUMCR 服務。
  
若要完成整合通訊設定，您還需要建立 UM 信箱原則，然後使用該原則來啟用使用者的整合通訊。您可使用類似下列的命令，來建立信箱原則：
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

您可使用類似下列的命令，來啟用使用者的整合通訊：
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

在上一個命令中，Extensions 參數代表使用者的電話分機號碼。在此範例中，使用者的分機號碼為 100。
  
啟用 kenmyer@litwareinc.com 的信箱後，該使用者應該就能使用 Exchange 整合通訊。 您可以從商務用 Skype Server 管理命令介面內執行[Test-CsExUMConnectivity](/powershell/module/skype/test-csexumconnectivity) Cmdlet，以確認使用者可以從 Exchange UM 進行連線：
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

若您還有第二個啟用了整合通訊的使用者，您可使用 [Test-CsExUMVoiceMail](/powershell/module/skype/test-csexumvoicemail) Cmdlet 來驗證第二個使用者是否能語音留言給第一個使用者。
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>設定 Microsoft Exchange Server 的整合通訊 
> [!IMPORTANT]
> 如果您想要使用 Exchange 整合通訊 (UM) 為企業語音使用者提供呼叫回應、Outlook 語音存取或自動語音應答服務，請參閱 Exchange 的[整合通訊整合對應](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)，然後遵循本節中的指示進行。 

若要設定 Exchange 整合通訊 (UM) 才能與企業語音搭配使用，您必須執行下列工作：

- 在執行 Exchange 整合通訊 (UM) 服務的伺服器上設定憑證
  > [!NOTE]
  > 將所有用戶端存取和信箱伺服器新增至所有 UM SIP URI 撥號對應表。 如果不是，則輸出通話路由不會如預期般運作。 
- 視需要建立一個或多個 UM SIP URI 撥號對應表，以及訂閱者存取電話號碼，然後建立對應的 L 撥號對應表。

- 使用 exchucutil.ps1 腳本執行下列作業：
    - 建立 UM IP 閘道。
    - 建立 UM 群組搜尋。
    - 授與讀取 UM Active Directory 網域服務物件的商務用 Skype Server 許可權。
- 建立 UM 自動語音應答物件。
- 建立訂閱者存取物件。
- 為每個使用者建立 SIP URI，並將使用者與 UM SIP URI 撥號對應表相關聯。

### <a name="requirements-and-recommendations"></a>需求和建議

在您開始之前，本節中的檔會假設您已部署下列 Exchange 角色： Client Access 和信箱。 在 Microsoft Exchange Server 中，Exchange UM 會在這些伺服器上以服務的身分執行。

也請注意以下事項：
- 如果 Exchange UM 安裝在多個樹系中，則必須針對每個 UM 樹系執行 Exchange Server 整合步驟。 此外，每個 UM 樹系都必須設定為信任部署商務用 Skype Server 的樹系，而且部署 whichSkype for Business Server 的樹系必須設定為信任每個 um 樹系。
- 在執行整合通訊服務的 Exchange Server 角色以及執行商務用 Skype Server 的伺服器上執行整合步驟。 您應該先執行 Exchange Server 的整合通訊整合步驟，再執行 Lync Server 2013 整合步驟。
  > [!NOTE]
  > 若要查看哪些伺服器及系統管理員角色上執行了哪些整合步驟，請參閱[整合內部部署整合通訊和商務用 Skype 的部署程式概述](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)。 

在執行 Exchange UM 的每一部伺服器上，都必須提供下列工具：
- Exchange 管理命令介面
- 指令碼 exchucutil.ps1，它會執行下列工作：
    - 為每個商務用 Skype Server 建立 UM IP 閘道。
    - 為每一個閘道建立群組搜尋。 每個群組搜尋的引導識別碼會指定與閘道相關聯之前端集區或 Standard Edition server 所使用的 UM SIP URI 撥號對應表。
    - 授與在 Active Directory 網域服務中讀取 Exchange UM 物件商務用 Skype Server 許可權。



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>使用 ExchUCUtil.ps1 設定 Microsoft Exchange 的整合通訊 

當您將 Microsoft 商務用 Skype Server 與 Exchange 整合通訊 (UM) 整合時，您必須在命令介面中執行 ExchUcUtil.ps1 腳本。 ExchUcUtil.ps1 指令碼可執行下列作業：

- 為每個商務用 Skype Server 集區建立 UM IP 閘道。

> [!IMPORTANT]
> ExchUcUtil.ps1 指令碼可建立一或多個 UM IP 閘道。 您必須在除了指令碼所建立的一個閘道以外的所有 UM IP 閘道上，停用撥出電話。 這包括在已於執行指令碼之前就建立的 UM IP 閘道上，停用撥出電話。 

- 為每個 UM IP 閘道建立一個 UM 群組搜尋。 每個群組搜尋的試驗識別碼會指定商務用 Skype Server 前端集區或與 um IP 閘道相關聯之 Standard Edition 伺服器所使用的 um SIP URI 撥號對應表。
- 授與讀取 Active Directory UM 容器物件（如 UM 撥號對應表、自動語音應答、um IP 閘道和 UM 群組搜尋）的商務用 Skype Server 許可權。
  > [!IMPORTANT]
  > 每個 UM 樹系都必須設定為信任部署商務用 Skype Server 的樹系，而且部署商務用 Skype Server 2013 的樹系必須設定為信任每個 um 樹系。 如果 Exchange UM 安裝在多個樹系中，則必須針對每個 UM 樹系執行 Exchange Server 整合步驟，否則您必須指定商務用 Skype Server 網域。 例如，ExchUcUtil.ps1 –樹系： \<lync-domain-controller-fqdn> 。 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>使用命令介面來執行 ExchUcUtil.ps1 指令碼

在組織中與商務用 Skype Server 位於相同拓撲的任何 Exchange 伺服器上，執行 ExchUcUtil.ps1 腳本。 您可以在 Mailbox Server 中使用命令介面來執行指令碼，或者您可以在 Client Access Server 上使用遠端 Windows PowerShell 來執行指令碼。 如果您在組織中的 Client Access Server 上執行指令碼，則 Client Access Server 會將遠端 Windows PowerShell 工作階段，Proxy 處理至組織中的 Mailbox Server。
> [!IMPORTANT]
> ExchUcUtil.ps1 指令碼可建立一或多個 UM IP 閘道。您必須在除了指令碼所建立的一個閘道以外的所有 UM IP 閘道上，停用撥出電話。這包括在已於執行指令碼之前就建立的 UM IP 閘道上，停用撥出電話。若要在 UM IP 閘道上停用撥出電話，請參閱停用 UM IP 閘道器上的撥出電話。[!IMPORTANT]
> 您必須具備「Exchange 組織管理」角色的權限或屬於 Exchange Organization Administrators 安全性群組的成員，才能執行此指令碼。 

1. 開啟 [Exchange 管理命令介面]。
2. 在 C：\ Windows \System32 提示中，輸入 **cd \<drive letter> ： \Program Files\Microsoft\ Exchange Server \V15\Scripts # C0.ExchUcUtil.ps1**，然後按 enter 鍵。

#### <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

若要確認是否已成功完成 ExchUcUtul.ps1 指令碼，請執行下列作業：
- 使用 Get-UMIPGateway Cmdlet 或 EAC 來檢視所建立的新 UM IP 閘道。
- 使用 Get-UMHuntGroup Cmdlet 或 EAC 來檢視所建立的新 UM 群組搜尋。

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>在執行 Exchange Server 整合通訊的伺服器上設定憑證
 
如果您已部署 Exchange 整合通訊 (UM) （如規劃檔中的「Exchange 整合通訊整合」中所述，以及您想要為組織中商務用 Skype Server 的使用者提供 Exchange UM 功能），您可以使用下列程式來進行 config在執行 Exchange UM 的伺服器上 ure 憑證。

> [!IMPORTANT]
> 針對內部憑證，執行商務用 Skype Server 的伺服器和執行 Microsoft Exchange 的伺服器必須具有相互信任的根信任授權憑證。 憑證授權單位單位 (CA) 可以相同或不同的憑證授權單位單位，只要伺服器在其受信任的根授權憑證存放區中註冊了憑證授權單位的根憑證。 

您必須使用伺服器憑證設定 Exchange Server，才能連線至商務用 Skype Server：
1. 下載 Exchange Server 的 CA 憑證。
2. 安裝 Exchange Server 的 CA 憑證。
3. 確認 CA 在 Exchange Server 的受信任的根 CA 清單中。
4. 建立 Exchange Server 的憑證要求並安裝憑證。 
5. 指派 Exchange Server 的憑證。


**若要下載 CA 憑證：**

1. 在執行 Exchange UM 的伺服器上，按一下 [**開始**]，按一下 [**執行**]，輸入 **HTTP:// \<name of your Issuing CA Server> /certsrv**，然後按一下 **[確定]**。
2. 在 [選取任務] 底下，按一下 [ **下載 CA 憑證、憑證鏈或 CRL**]。
3. 在 [ **下載 Ca 憑證、憑證鏈或 CRL**] 底下，選取 [ **編碼方式為 64**]，然後按一下 [**下載 CA 憑證**]。
   > [!NOTE]
   > 您也可以在此步驟中指定可辨別編碼規則 (DER) 編碼。 如果您選取 DER 編碼，此程序下一個步驟中以及 **「若要安裝 CA 憑證」** 步驟 10 中的檔案類型會是 .p7b，而非 .cer。 
4. 在 **[檔案下載]** 對話方塊中，按一下 **[儲存]**，然後將檔案儲存到伺服器的硬碟上 (視您在上一個步驟中選取的編碼而定，檔案的副檔名會是 .cer 或 .p7b)。

**若要安裝 CA 憑證：**

1. 在執行 Exchange UM 的伺服器上，按一下 [**開始**]，按一下 [**執行**]，然後在 [開啟] 方塊中輸入 **MMC** ，然後按一下 **[確定]**，以開啟 Microsoft Management Console (MMC) 。
2. 在 **[檔案]** 功能表中，按一下 **[新增/移除嵌入式管理單元]**，然後按一下 **[新增]**。
3. 在 **[新增獨立嵌入式管理單元]** 方塊中，按一下 **[憑證]**，然後按一下 **[新增]**。
4. 在 **[憑證嵌入式管理單元]** 對話方塊中，按一下 **[電腦帳戶]**，然後按 **[下一步]**。
5. 在 [ **選取電腦** ] 對話方塊中，確認已選取 [ **本機電腦： (執行此主控台的電腦)** ] 核取方塊，然後按一下 **[完成]**。
6. 按一下 **[關閉]**，然後按一下 **[確定]**。 
7. 在主控台樹狀目錄中，依序展開 **[憑證 (本機電腦)]** 和 **[信任的根憑證授權]**，然後按一下 **[憑證]**。
8. 以滑鼠右鍵按一下 **[憑證]**，按一下 **[所有工作]**，再按一下 **[匯入]**。
9. 按 **[下一步]**。 
10. 按一下 **[瀏覽]**，找出檔案，然後按 **[下一步]** (視您在 **「若要下載 CA 憑證」** 步驟 3 中選取的編碼而定，檔案的副檔名會是 .cer 或 .p7b)。
11. 按一下 [ **將所有憑證放** 入下列儲存區]。
12. 按一下 **[瀏覽]**，然後選取 **[受信任的根憑證授權單位]**。 
13. 按 **[下一步]** 以驗證設定，然後按一下 **[完成]**。 


**若要驗證 CA 是否在受信任的根 Ca 清單中：**

1. 在執行 Exchange UM 的伺服器上，于 MMC 中展開 [憑證 (本機電腦) ]，然後展開 [信任的根憑證授權單位]，然後按一下 [憑證]。
2. 在詳細資料窗格中，確認您的 CA 位於受信任的 CA 清單上。