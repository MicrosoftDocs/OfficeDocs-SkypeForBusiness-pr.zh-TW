---
title: 部署商務用 Skype Server 中的 Skype 連線能力
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 摘要：瞭解如何使用 Skype 消費者來連接商務用 Skype Server。 也稱為 Skype 連線性。
ms.openlocfilehash: c8bdbf96fcbf0831433ad2274d8ab89911df1de5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835821"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>部署商務用 Skype Server 中的 Skype 連線能力

**摘要：** 瞭解如何使用 Skype 消費程式來連接商務用 Skype Server。 也稱為 Skype 連線性。
  
本文將引導您部署 Skype 連線性。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>SkypeIT 專業人員的連線能力一覽

Skype連線能力為商務用 Skype 使用者提供搜尋及新增 Skype 使用者的能力。 Skype連線功能是商務用 Skype 的功能，可讓您使用 Skype 使用者啟用同盟及目錄搜尋。 在您啟用 Skype 連線功能之後，您商務用 Skype 使用者就能夠搜尋及新增 Skype 使用者。
  
## <a name="skype-directory-search"></a>Skype目錄搜尋

Skype目錄搜尋功能可讓商務用 Skype 使用者能夠搜尋 Skype 連絡人。 搜尋功能可讓使用者使用下列專案進行搜尋：
  
- **依顯示名稱搜尋，例如「John Doe** 」-這可能會傳回許多結果，所以您可能不會找到您要尋找的專案。
    
- **依顯示名稱加上位置進行搜尋，範例「John Doe 為巴塞羅納** 」-這會大幅縮小搜尋的結果。
    
- **依電子郵件搜尋，範例 "johndoe@outlook.com"** -在大多數情況下，這應該會傳回一個結果。與指定之電子郵件完全相符的專案。 不過，如果相同的電子郵件與一個以上的帳戶相關聯，則可能會傳回多個結果。
    
- **依電話號碼搜尋（範例 "123-123-1234"），** 在大多數情況下，這應該會傳回一個結果。完全符合指定電話的一種。 電話號碼必須包含國家/地區代碼 (（即 1-xxx-yyy-zzzz) ）。 如果相同的電話號碼與一個以上的帳戶相關聯，則可能會傳回多個結果。
    
- **依 Skype 名稱搜尋例如，"JohnDoe1456"** -如果找到完全相符的文字，則會傳回為第一個結果。 可能會傳回其他可能的「名稱」相符專案。
    
    > [!NOTE]
    > Skype目錄搜尋必須能夠與埠443上的下列 IP 位址通訊：104.40.75.246、23.101.135.34 及40.113.86.19。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype 目錄搜尋支援的部署矩陣

下表概述 Skype 目錄搜尋的支援。
  

|&nbsp;|商務用 Skype Server前端|Lync Server 2013 (或舊版) 前端|註解|
|:-----|:-----|:-----|:-----|
|商務用 Skype Server邊緣   |支援   |不支援   |商務用 Skype Server 和 Edge 是 Skype 目錄搜尋的必要條件   |
|商務用 Skype ServerEdge + Lync Server 2013 Edge 已並行部署   |支援   |不支援   |Skype目錄搜尋流量流經商務用 Skype Server Edge server。 同盟流量會透過系統管理員設定的 edge 進行。 例如，管理員可以選擇繼續透過 Lync Server 2013 Edge server 傳送同盟流量，這不會支援 Skype 目錄搜尋。   |
|Lync Server 2013 (或舊版) Edge   |不支援   |不支援   ||
   
> [!NOTE]
> 在商務用 Skype Server 前端執行的 Addressbook 服務會根據 edge Server 中是否存在 Skype 搜尋埠4443尋找 edge。 
  
> [!NOTE]
> 若客戶在其內部部署中有多個網站，而且他們只部署了一個商務用 Skype Server Edge server/集區，則從所有網站搜尋流量會透過單一可用的 edge server。 管理員需要確定所有網站的集區都可以存取已部署的商務用 Skype Server Edge Server/集區。 
  
> [!NOTE]
> Skype graph 服務會限制任何內部部署或 Microsoft 365 或 Office 365 客戶的搜尋要求（如果要求率超過15個要求/秒）。 
  
> [!NOTE]
> 針對大型企業內部部署客戶，您必須使用 Skype 搜尋服務將網域新增至 allowlist，以允許更高的要求率。
  
> [!NOTE]
> 如果佇列中有太多擱置要求，商務用 Skype Server 會節流傳入的要求。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>部署商務用 Skype 線上的 Skype 連線能力

Skype連線也是商務用 Skype 線上的功能，也就是 Microsoft 365 和 Office 365 的一部分。 您可以從 Microsoft 365 系統管理中心中的商務用 Skype 系統管理中心，啟用 Skype Connectivity 功能。
  
如需 Microsoft 365 的中型企業版、Office 365 企業版、Microsoft 365 教育版及 Office 365 的政府版：登入 Microsoft 365 系統管理中心，然後流覽至商務用 Skype 管理中心。 移至 [外部通訊]。 在 [公用 IM 服務提供者] 底下，按一下 [啟用]。 如果您想要控制個別使用者對 Skype 連線的存取，您可以編輯個別使用者的外部通訊設定來執行此動作。
  
若為 Office 365 Small Business Premium：登入 Office 365，然後移至系統管理 \> 服務設定 \> 立即訊息、會議和會議。 開啟外部通訊。 外部通訊參數會同時開啟 Skype 連線，以及與使用商務用 Skype 的其他組織通訊。
  
如需商務用 Skype 線上管理的詳細資訊，請參閱：
  
- [允許使用者連絡外部商務用 Skype 使用者](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [當您無法以 IM 商務用 Skype 或 Skype 外部連絡人時，要嘗試的做法](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [在商務用 Skype 中新增連絡人](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Admins：設定個別使用者的商務用 Skype 設定](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>部署商務用 Skype Server 的 Skype 連線能力

商務用 Skype Server 會使用同盟存取架構，以支援與 Skype 的連接。 這可讓您的商務用 Skype Server 使用者新增 Skype。 Skype 用戶端也可以將商務用 Skype 使用者新增至其連絡人清單。 根據商務用 Skype Server 使用者中的管理原則，可使用立即訊息進行通訊、查看彼此的狀態，以及啟動音訊和影片通話。 Skype 連線也是商務用 Skype 線上的功能，而且可以從 Microsoft 365 系統管理中心內的商務用 Skype 系統管理中心，商務用 Skype 線上客戶進行啟用。
  
> [!NOTE]
> 如果商務用 Skype Server 已設定為使用公用立即訊息連線 (PIC) 來連接 Windows Messenger，您的部署已設定為 Skype 連線性。 您可能會考慮將現有的 Messenger PIC 專案重新命名為 Skype。 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>已無法再使用商務用 Skype Server 公用 IM 連線布建網站

先前用於在商務用 Skype 內部部署與 Skype 之間手動布建同盟的網站，已不再需要，且會在8/15/2019 上關機。 同盟 with Skype 現在會利用同盟協力廠商探索，這是與商務用 Skype Online 同盟所需的相同機制。

任何內部部署商務用 Skype 部署與透過現有公用 IM 基礎結構 Skype 使用者之間的通訊現在，都需要內部部署 Edge Server 設定與商務用 Skype 線上相容。

> [!NOTE]
> 大多數客戶不需要執行任何動作，包括與商務用 Skype 線上的所有部署。
  
內部部署是針對其所裝載的每個網域，發佈同盟 DNS SRV 記錄所需的。 在 [DNS 規劃](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)中提供指導方針。 每個網域都必須由 DNS SRV 查詢解析為滿足網域的最上層尾碼比對之 edge server FQDN。 例如，請考慮網域 "contoso.com"：

|**有效 Fqdn**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |在每個案例中，確切的 FQDN 都必須存在於安裝在 edge server 上之外部憑證的 SN 或 SAN 中。   |
|access.contoso.com   ||
|**不正確 Fqdn**|**原因**|
|sip.contoso-edge.com   |非尾碼相符。  |
|sip.it.contoso.com   |不是最上層尾碼相符。   |

您可以在 [認證規劃](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)中找到外部憑證的相關指引。

#### <a name="faqs"></a>常見問題集

**為何要關閉布建網站？**
在2006中部署的公用 IM (PIC) 布建機制 (pic.lync.com) 已無法繼續維護，且會在8/15/2019 時關閉。 相反地，公用 IM 同盟會假設商務用 Skype Online （稱為「夥伴探索」）所使用的相同同盟模型，因此內部部署部署會透過其同盟 DNS SRV 記錄 (s) 加以公開探索。

**這種變更意味著公用 IM 同盟被取代？**
否。 公用 IM 同盟將繼續支援許多年，直到商務用 Skype 的內部部署產品到達生命週期結束時為止。

**我們公司有 (共用位址空間的混合式關聯) 商務用 Skype 線上，我們會受到影響嗎？**
不需要，因為您已與商務用 Skype 線上，所以此變更不會影響您。
 
**這種變更是否意味著公司必須啟用與商務用 Skype 線上的同盟？**
否。 如果您的 edge server proxy 設定沒有啟用與商務用 Skype Online 主機服務提供者的同盟 (sipfed.online.lync.com) 則此變更不會影響。 不過，與商務用 Skype Online 進行同盟的相同 DNS 和憑證需求現在也適用于與 Skype 使用者的聯盟。
 
**我們公司很大，無法變更其 edge 設定，因為規定/合規性/etc 原因 .。。我們可以做什麼？**
任何內部部署組織若不能根據指定變更其 edge server 設定，應儘早到達產品支援服務。

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>啟用同盟和公用 IM 連線 (PIC) 

現在著重于設定 Skype 連線所需的商務用 Skype Server 環境和系統管理工作。 在本節中，我們假設系統管理員已部署商務用 Skype Server 和設定的外部存取（也稱為 Edge server）。 
  
有三個主要步驟必須啟用同盟和 PIC。 如下所述：
  
1. 設定同盟和 PIC
    
2. 設定至少一個原則以支援同盟使用者存取
    
3. 設定 Skype PIC 提供者設定
    
#### <a name="1-configure-federation-and-pic"></a>1. 設定同盟和 PIC

需要同盟才能讓 Skype 使用者與您組織中的商務用 Skype 使用者通訊。 公用立即訊息連線 (PIC) 是同盟的類別，必須加以設定，才能讓商務用 Skype 使用者能夠與 Skype 使用者通訊。 同盟和 PIC 是使用商務用 Skype Server 控制台設定。
  
> [!NOTE]
> Lync server 2010 (Live Communication server 之前，產品版本已不再支援 PIC 同盟（Office 通訊伺服器) ）。 支援的 PIC 同盟平臺包括商務用 Skype Server、lync server 2013 和 lync server 2010。 
  
需要同盟才能讓 Skype 使用者與您組織中的商務用 Skype 使用者通訊。 公用立即訊息連線 (PIC) 是同盟的類別，必須加以設定，才能讓商務用 Skype Server 使用者能夠與 Skype 使用者通訊。 同盟和 PIC 的設定方式是使用商務用 Skype Server 控制台的 [Edge 設定] 對話方塊如圖所示。
  
![定義新的 Edge 集區。](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> EnableSkypeIdRouting 和 EnableSkypeDirectorySearch 屬性必須設定為 true 中的公用提供者設定 (請參閱後續指示) 供搜尋正常運作。 
  
這會完成必須在伺服器上執行的管理工作。 您現在已設定 Skype 連線能力。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. 設定至少一個原則以支援同盟使用者存取

使用商務用 Skype Server 控制台，管理員必須設定一或多個外部使用者存取原則，以控制 Skype 使用者是否可以與內部商務用 Skype Server 使用者共同作業。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. 設定 Skype PIC 提供者設定

管理員必須使用商務用 Skype Server 管理命令介面，設定商務用 Skype 用戶端原則，以將 Skype 顯示為其他 PIC 提供者。 
  
> [!NOTE]
>  (PIC) 服務提供者的公用立即訊息連線使用者無法參與您組織中的 IM 或會議，除非您在此程式之前設定至少一個原則 (步驟2，) 以支援公用 IM 連線能力。 
  
針對新的安裝，您可以使用商務用 Skype Server 控制台來啟用 Skype 公用提供者，以設定 Skype 連線能力，如圖所示。
  
![SIP 同盟提供者。](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> 若要在升級至商務用 Skype Server 時設定 Skype 連線能力，您必須移除並重新新增現有的 Skype 公開提供者。 
  
設定 Skype 連線能力也可以僅使用 PowerShell 進行。 使用 PowerShell: 設定 Skype 連通性
  
1. 從商務用 Skype Server 前端伺服器，開啟商務用 Skype Server 管理命令介面。
    
2. 執行下列兩個命令：
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 如果您的環境中已沒有 PIC 提供者，且正在建立新的 PIC 提供者，則不需要執行 Remove-CsPublicProvider Cmdlet。 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    不太明顯的參數會有什麼用處？
    
   - ProxyFqdn： Microsoft 所擁有/維護 (Skype 同盟 edge 的位置) 
    
   - IconURL： Lync &amp; 商務用 Skype 用戶端用來以視覺方式識別 Skype 連絡人的圖示
    
   - NameDecorationRoutingDomain 與 NameDecorationExcludedDomainList：設定這些功能可讓使用者輸入 Skype 使用者的 MSAs，而不需要知道「修飾」非 Microsoft 網域與「msn.com」。 這樣就不需要為 ExcludedDomainList 以外的所有網域輸入「使用者 (contoso.com) @msn .com」。 當網域不在排除清單中時，SfB 用戶端會自動格式化 MSA。 我們已將最常見的 Microsoft 帳戶網域新增至排除清單。
    
     > [!NOTE]
     > 若要進行變更，必須移除公用提供者並新增新的提供者。 不允許就地變更。 
  
     > [!NOTE]
     > 新增于 lync Server 2013 CU5 &amp; lync 桌面用戶端中 Office 2013 SP1，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 可改善 lync 使用者新增 Skype 連絡人所需的情況，使其「修飾」非 Microsoft 網域，以找出並路由傳送至 Skype ( (的格式： user) contoso.com @msn) .com。 在 [新增 Skype 連絡人] (對話方塊中，這些新設定將允許自動設定位址使用者輸入的格式，如果不包含 (NameDecorationExcludedDomainList 中的網域，則應設定為 msn.com) （如果目前可支援 msn.com、live.com、Hotmail.com、outlook.com) ）。 
  
3. 從商務用 Skype 用戶端使用者現在可以搜尋並新增 Skype 使用者。
    
## <a name="clients-and-interoperability-matrix"></a>用戶端和互通性清單

下表概述 Skype 消費程式最新版本與最新版商務用 Skype 之間的交互操作狀態。
  

|Skype客戶|新增連絡人、IM、顯示狀態、音訊和影片通話|留言|
|:-----|:-----|:-----|
|Skype Windows 桌面   |7.6 或更高版本 Windows XP 及更高版本   |**新增**：針對執行于 Windows XP 上的 Windows Skype 用戶端，新增支援，而 Windows Vista **(需要最新的用戶端版本7.26 或更高版本)**  |
|SkypeMobile-Android 電話和平板電腦   |6.19 或更高版本，執行 Android OS 版本4.0.3 或更高版本   |低規格裝置可能不支援影片通話   |
|Skype行動裝置 iOS   |IOS 7 或更高版本上的6.11 或更高版本   |不支援的 iPhone 4 及更早版本、iPod 第四代及更早版本 iPad 第一代   |
|SkypeMac   |7.19 或更高版本，Mac OS X 10.9 (Mavericks) 或更高版本   |需要 Mac OSX 10.9 或更高版本   |
|Skype通用 Windows App (Windows 10) 桌面和行動裝置   |Windows 10 (Redstone 1 更新或更新版本)    |Windows通用應用程式會在秋季2016接收更新新增 interop 支援   |
   
下表說明最新版商務用 Skype 與最新版本 Skype 消費者之間的交互操作狀態。 
  
|用戶端|Skype目錄搜尋及新增連絡人|SkypeA/V，IM interop|
|:-----|:-----|:-----|
|商務用 Skype   |是   |是   |
|Mac 版商務用 Skype   |可以新增 (無搜尋)    |是   |
|Lync 桌面2013   |可以新增 (無搜尋)    |是   |
|Lync Web App-線上和內部部署   |不適用   |不適用   |
|Lync Mobile-Windows Phone   |即將推出   |是   |
|Lync Mobile-Android   |即將推出   |是   |
|Lync Mobile-iOS   |即將推出   |是   |
|Lync Room System   |即將推出   |是   |
|Lync 新式應用程式 (Win 8.1)    |是   |是   |
|Lync Mac 2011   |可以新增 (無搜尋)    |是   |
|Lync 桌面2010   |可以新增 (無搜尋)    |是   |
|Lync Phone Edition   |不適用   |不適用   |
|Lync 語音應答   |不適用   |不適用   |
   
