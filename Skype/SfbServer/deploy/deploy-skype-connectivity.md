---
title: 在商務用 Skype Server 中部署 Skype 連線能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 摘要：瞭解如何將商務用 Skype 伺服器與 Skype 消費者連線。 也稱為 Skype 連線。
ms.openlocfilehash: e9c8a83b24ddbed95f2fd16f2f11b887f2241625
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798100"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>在商務用 Skype Server 中部署 Skype 連線能力

**摘要：** 瞭解如何將商務用 Skype 伺服器與 Skype 消費者連線。 也稱為 Skype 連線。
  
本文將引導您逐步取得 Skype 連線性部署。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>IT 專業人員的 Skype 連線性概述

Skype 連線能力為商務用 Skype 使用者提供搜尋及新增 Skype 使用者的功能。 Skype 連線能力是商務用 Skype 的一項功能，可讓您使用 Skype 使用者來啟用聯盟和目錄搜尋。 啟用 Skype 連線之後，您的商務用 Skype 使用者就可以搜尋並新增 Skype 使用者。
  
## <a name="skype-directory-search"></a>Skype 目錄搜尋

Skype 目錄搜尋功能可為商務用 Skype 使用者提供搜尋 Skype 連絡人的功能。 [搜尋] 功能可讓使用者使用下列動作進行搜尋：
  
- **依顯示名稱搜尋，例如「John Doe** 」-這可能會傳回許多結果，因此您可能找不到您要尋找的專案。
    
- **依顯示名稱加上位置來搜尋，範例「John 在巴塞羅納內 Doe** 」-這將大大縮小搜尋結果的範圍。
    
- **依電子郵件搜尋，例如「johndoe@outlook.com** 」-這應該在大多數情況下傳回一個結果;與指定的電子郵件完全相符的專案。 但是，如果同一個電子郵件與一個以上的帳戶相關聯，可能會傳回多個結果。
    
- **依電話號碼搜尋，例如「123-123-1234** 」-這應該在大多數情況下傳回一個結果;與指定的電話完全相符的一個。 電話號碼必須包含國家/地區代碼（亦即 1 xxx-zzzz）。 如果相同的電話號碼與一個以上的帳戶相關聯，可能會傳回多個結果。
    
- **依 Skype 名稱搜尋，例如 "JohnDoe1456"** -如果找到完全相符的專案，則會傳回第一個結果。 可能會傳回其他可能的「名稱」相符專案。
    
    > [!NOTE]
    > Skype 目錄搜尋必須能夠與埠443：104.40.75.246、23.101.135.34 和40.113.86.19 中的下列 IP 位址進行通訊。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype 目錄搜尋支援的部署矩陣

下表概述 Skype 目錄搜尋的支援。
  

||**商務用 Skype Server 前端**|**Lync Server 2013 （或較舊版本）前端**|**批註**|
|:-----|:-----|:-----|:-----|
|商務用 Skype Server Edge  <br/> |受  <br/> |不支援  <br/> |商務用 skype Server 和 Edge 是 Skype 目錄搜尋的先決條件  <br/> |
|商務用 Skype Server Edge + Lync Server 2013 Edge 並排部署  <br/> |受  <br/> |不支援  <br/> |Skype 目錄搜尋流量透過商務用 Skype Server Edge 伺服器進行流動。 同盟流量會透過系統管理員設定的邊緣進行。 例如，管理員可以選擇繼續透過不支援 Skype 目錄搜尋的 Lync Server 2013 Edge 伺服器傳送同盟通訊。  <br/> |
|Lync Server 2013 （或較舊版本）邊緣  <br/> |不支援  <br/> |不支援  <br/> ||
   
> [!NOTE]
> 在商務用 Skype Server 前端執行的 Addressbook 服務在 Edge 伺服器中存在 Skype 搜尋埠4443，即可找出邊緣。 
  
> [!NOTE]
> 如果客戶在其內部部署部署中有多個網站，而且他們已部署的是一個商務用 Skype Server Edge 伺服器/池，則從所有網站搜尋流量都會透過單一可用的邊緣伺服器。 系統管理員必須確認所有網站的池都能存取已部署的商務用 Skype Server Edge 伺服器/池。 
  
> [!NOTE]
> 如果要求率超過15個要求/秒，Skype graph 服務將會限制來自任何內部部署或 Office 365 客戶的搜尋要求。 
  
> [!NOTE]
> 針對大型企業內部部署客戶，網域需要使用 Skype 搜尋服務進行白名單，以允許較高的要求。 
  
> [!NOTE]
> 如果佇列中有太多掛起的要求，商務用 Skype 伺服器將會調解傳入的要求。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>在 Office 365 中部署商務用 Skype Online 的 Skype 連線

Skype 連線能力也是商務用 Skype Online 的一項功能，也就是 Office 365 的一部分。 您可以從 Office 365 入口網站中的商務用 Skype 系統管理中心啟用 Skype 連線功能。
  
針對 Office 365 中型企業版、Office 365 Enterprise、Office 365 教育版和 Office 365 for 政府版：登入 Office 365 入口網站，然後流覽至商務用 Skype 系統管理中心。 移至 [外部通訊]。 在 [公用 IM 服務提供者] 底下，按一下 [啟用]。 如果您想要控制個別的使用者對 Skype 連線的存取權，您可以編輯個別使用者的 [外部通訊] 設定來執行此動作。
  
針對 Office 365 小型企業版 Premium：登入 Office 365，然後移至 [ \>管理員服務\>設定立即訊息、會議和會議]。 開啟 [外部通訊]。 外部通訊開關會開啟 Skype 連線，以及與使用商務用 Skype 的其他組織進行通訊。
  
如需商務用 Skype Online 系統管理的詳細資訊，請參閱：
  
- [允許使用者連絡外部商務用 Skype 使用者](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [如果您無法傳送商務用 Skype 或 Skype 外部連絡人的 IM，該嘗試什麼方法](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [在商務用 Skype 中新增連絡人](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [系統管理員：針對個別使用者設定商務用 Skype 設定](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>部署商務用 Skype Server 的 Skype 連線

商務用 skype 伺服器使用同盟存取架構來支援與 Skype 的連線。 這個連線功能可讓您的商務用 Skype 伺服器使用者新增 Skype。 Skype 用戶端也可以將商務用 Skype 使用者新增至其連絡人清單。 根據商務用 Skype Server 使用者的系統管理員設定，您可以使用立即訊息進行通訊、查看彼此的目前狀態，以及啟動音訊與視頻通話。 Skype 連線也是商務用 Skype Online 的一項功能，而且可在 Office 365 入口網站中的商務用 Skype 系統管理中心的商務用 skype Online 客戶中啟用。
  
> [!NOTE]
> 如果商務用 Skype 伺服器已設定為使用公用立即訊息連線（PIC）與 Windows Messenger 進行連線，您的部署已設定為 Skype 連線。 唯一需要考慮進行的變更就是將現有的 Messenger PIC 項目重新命名為 Skype。 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>商務用 Skype Server 公用 IM 連線提供網站已不再提供

先前曾用來在商務用 Skype 內部部署與 Skype 之間手動設定同盟的網站，將不再需要，且會在8/15/2019 上關閉。 使用 Skype 的同盟現已使用聯盟合作夥伴探索，這是與商務用 Skype Online 進行聯盟所需的相同機制。

您可以透過現有的公用 IM 基礎結構，在任何內部部署商務用 Skype 部署與 Skype 使用者之間進行通訊，現在需要與商務用 Skype Online 相容的內部部署邊緣伺服器設定。

> [!NOTE]
> 大多數客戶不需要採取任何動作，包括與商務用 Skype Online 進行聯盟的所有部署。
  
若要為其主持的每個網域發佈同盟 DNS SRV 記錄，都需要內部部署部署。 您可以在[DNS 規劃](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)中取得指導方針。 每個網域都必須由 DNS SRV 查詢解析至 edge 伺服器 FQDN，以符合網域的頂層尾碼相符。 例如，請考慮網域 "contoso.com"：

|**有效 Fqdn**|**評論**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |在每個情況下，確切的 FQDN 都必須存在於安裝于 edge 伺服器的外部憑證的 SN 或 SAN 中。   |
|access.contoso.com   ||
|**不正確 Fqdn**|**不必**|
|sip.contoso-edge.com   |不是尾碼相符。  |
|sip.it.contoso.com   |不是最上層尾碼相符的專案。   |

您可以在 [[認證規劃](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)] 中找到有關外部憑證的進一步指導方針。

#### <a name="faqs"></a>常見問題

**為什麼正在關閉 [預配] 網站？**
在2006中部署的公用 IM （PIC）自動設定機制（pic.lync.com）已不再提供維修，且會在8/15/2019 上關閉。 相反地，公用 IM 同盟會採用商務用 Skype Online 所使用的相同同盟模型（稱為「合作夥伴探索」），因此內部部署的部署是透過其同盟 DNS SRV 記錄來公開發現的。

**此變更表示已棄用公用 IM 同盟嗎？**
不。 公用 IM 同盟將持續支援許多年，可能直到商務用 Skype 內部部署產品達到使用期結束。

**我們的公司與商務用 Skype Online 有混合式關聯（共用位址空間），我們會受到影響嗎？**
不行，因為您已與商務用 Skype Online 進行聯盟，所以此變更不會影響您。
 
**此變更表示我們的公司必須啟用與商務用 Skype Online 的同盟？**
不。 如果您的 edge 伺服器 proxy 設定沒有啟用與商務用 Skype Online 主機服務提供者（sipfed.online.lync.com）的同盟，就不會影響這項變更。 不過，套用來與商務用 Skype Online 進行聯盟的 DNS 和憑證需求現在也適用于與 Skype 使用者進行聯盟。
 
**我們的公司很大，因此由於監管/合規性或等原因而無法變更其邊緣設定 .。。我們可以做什麼？**
任何不能根據指定變更 edge 伺服器設定的內部部署組織，都應該儘早向產品支援部門取得。

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>啟用同盟與公用 IM 連線（PIC）

現在，我們將焦點放在商務用 Skype Server 環境和設定 Skype 連線所需的管理工作上。 在本節中，我們假設系統管理員已部署商務用 Skype Server 及設定的外部存取，也稱為 Edge 伺服器。 
  
若要啟用同盟和 PIC，必須執行三個主要步驟。 這些是：
  
1. 設定同盟與 PIC
    
2. 至少設定一個要支援同盟使用者存取的原則
    
3. 設定 Skype PIC 提供者設定
    
#### <a name="1-configure-federation-and-pic"></a>1. 設定同盟與 PIC

必須具備同盟，才能讓 Skype 使用者與您組織中的商務用 Skype 使用者通訊。 公用立即訊息連線（PIC）是一種同盟類別，而且必須加以設定，才能讓您的商務用 Skype 使用者與 Skype 使用者通訊。 [同盟] 和 [PIC] 是使用商務用 Skype Server 的 [控制台] 進行設定。
  
> [!NOTE]
> Lync Server 2010 （Live Communication Server、Office 通訊伺服器）之前的產品發行已不再支援 PIC 同盟。 適用于 PIC 同盟的支援平臺包括商務用 Skype Server、Lync Server 2013 和 Lync Server 2010。 
  
必須具備同盟，才能讓 Skype 使用者與您組織中的商務用 Skype 使用者通訊。 公用立即訊息連線（PIC）是一種同盟類別，而且必須設定，才能讓您的商務用 Skype 伺服器使用者與 Skype 使用者通訊。 同盟和 PIC 是使用商務用 Skype Server [控制台] 的 [邊緣設定] 對話方塊來設定，如下圖所示。
  
![定義新的邊緣池](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 在公用提供者設定（請參閱稍後的指示）中，EnableSkypeIdRouting 和 EnableSkypeDirectorySearch 屬性必須設定為 true，才能讓搜尋正常運作。 
  
這樣就完成了必須在伺服器上執行的系統管理工作。 您現在已設定 Skype 連線。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. 設定至少一個原則以支援同盟使用者存取

在商務用 Skype Server [控制台] 中，系統管理員必須設定一或多個外部使用者存取原則，以控制 Skype 使用者是否可與內部商務用 Skype 伺服器使用者共同作業。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. 設定 Skype PIC 提供者設定

在商務用 Skype Server Management 命令介面上，系統管理員必須設定商務用 Skype 用戶端原則，才能將 Skype 顯示為額外的 PIC 提供者。 
  
> [!NOTE]
> 公用立即訊息連線（PIC）服務提供者的使用者無法在您的組織中參與 IM 或會議，除非您在此程式中設定至少一個原則（步驟2），才能支援公用 IM 連線。 
  
在新的安裝中，您可以使用商務用 Skype Server [控制台] 啟用 Skype 公用提供者來設定 Skype 連線，如圖所示。
  
![SIP 同盟提供者](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> 若要在升級至商務用 Skype Server 時設定 Skype 連線，您必須移除並重新新增現有的 Skype 公用提供者。 
  
您也可以使用 [僅限 PowerShell] 來設定 Skype 連線。 若要使用 PowerShell 設定 Skype 連線：
  
1. 從商務用 Skype Server 前端伺服器開啟商務用 Skype Server 管理命令介面。
    
2. 執行下列兩個命令：
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 如果您的環境中還沒有 PIC 提供者，且正在建立新的 PIC 提供者，則不需要執行 CsPublicProvider Cmdlet。 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    不太明顯的參數有何用處？
    
   - ProxyFqdn： Skype 同盟 edge 的位置（由 Microsoft 擁有/維護）
    
   - IconURL： Lync &amp;商務用 Skype 用戶端使用的圖示，以視覺方式識別 Skype 連絡人
    
   - NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList：設定這些功能可讓使用者輸入 Skype 使用者的 MSAs，而不需要瞭解「修飾」非 Microsoft 網域與 "msn.com"。 這樣就不需要在 ExcludedDomainList 以外的所有網域中輸入「user （contoso） @msn .com」。 如果網域不在排除清單中，SfB 用戶端會自動設定 MSA 的格式。 我們已將最常見的 Microsoft 帳戶網域新增到排除清單中。
    
     > [!NOTE]
     > 如果進行變更，必須移除公用提供者並新增新的提供者。 不允許就地變更。 
  
     > [!NOTE]
     > 在 Lync Server 2013 中新增&amp; OFFICE 2013 SP1 中的 CU5 lync 桌面用戶端，這會改善 lync 使用者新增必要的 skype 連絡人至「保密協定」，以找出並將其路由至 Skype （格式為：使用者（contoso .com） @msn .com）。 這些新設定可讓您在 [新增 Skype 連絡人] 對話方塊中的 [新增 Skype 連絡人] 對話方塊中，自動設定位址格式，但如果它不包含 NameDecorationExcludedDomainList 中的網域，則為 NameDecorationRoutingDomain （應設定為 msn.com）。我們目前可以支援 msn.com、live.com、Hotmail.com、outlook.com）。 
  
3. 從商務用 Skype 用戶端的使用者現在可以搜尋並新增 Skype 使用者。
    
## <a name="clients-and-interoperability-matrix"></a>用戶端與互通性矩陣

下表列出最新版 Skype 消費者與最新版商務用 Skype 之間互通性的狀態。
  

|**Skype 用戶端**|**新增連絡人、IM、目前狀態、音訊及視頻通話**|**評論**|
|:-----|:-----|:-----|
|Skype Windows 電腦版  <br/> |7.6 或更新版本、Windows XP 及更高版本  <br/> |**新**：針對執行 windows XP 的 windows Skype 用戶端及 windows Vista **（需要最新的用戶端版本7.26 或更高版本）** 新增支援 <br/> |
|Skype Mobile-Android 手機和平板電腦  <br/> |6.19 或更高版本，執行 Android OS 版本4.0.3 或更新版本  <br/> |低規範裝置可能不支援視頻通話  <br/> |
|Skype Mobile-iOS  <br/> |IOS 7 或更新版本上的6.11 或更新版本  <br/> |不支援的版本為 iPhone 4 及較舊版本、iPod 第4代及更舊版本、iPad 第1代  <br/> |
|Skype Mac  <br/> |7.19 或更新版本（Mac OS X 10.9 （Mavericks）或更高版本  <br/> |需要 Mac OSX 10.9 或更新版本  <br/> |
|Skype 通用 Windows 應用程式（Windows 10）桌面和行動裝置  <br/> |Windows 10 （Redstone 1 更新版或更新版本）  <br/> |Windows 通用 App 將會在秋季2016中接收更新，以新增互通性支援  <br/> |
   
下表列出最新版本的商務用 Skype 與最新版 Skype 消費者之間互通性的狀態。 
  
|**用戶端**|**Skype 目錄搜尋及新增連絡人**|**Skype A/V、IM 互通性**|
|:-----|:-----|:-----|
|商務用 Skype  <br/> |是  <br/> |是  <br/> |
|Mac 上的商務用 Skype  <br/> |可以新增（無搜尋）  <br/> |是  <br/> |
|Lync 桌面2013  <br/> |可以新增（無搜尋）  <br/> |是  <br/> |
|Lync Web App-線上與內部部署  <br/> |不適用  <br/> |不適用  <br/> |
|Lync Mobile-Windows Phone  <br/> |即將推出  <br/> |是  <br/> |
|Lync Mobile-Android  <br/> |即將推出  <br/> |是  <br/> |
|Lync Mobile-iOS  <br/> |即將推出  <br/> |是  <br/> |
|Lync 會議室系統  <br/> |即將推出  <br/> |是  <br/> |
|Lync 現代應用程式（Win 8.1）  <br/> |是  <br/> |是  <br/> |
|Lync Mac 2011  <br/> |可以新增（無搜尋）  <br/> |是  <br/> |
|Lync 桌面2010  <br/> |可以新增（無搜尋）  <br/> |是  <br/> |
|Lync Phone Edition  <br/> |不適用  <br/> |不適用  <br/> |
|Lync 助理  <br/> |不適用  <br/> |不適用  <br/> |
   

