---
title: 商務伺服器部署中 Skype Skype 連線能力
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
description: 摘要： 了解如何與 Skype 消費者連線 Skype for Business Server。 也稱為 Skype 連線。
ms.openlocfilehash: be53acc531d0abb789ae4e622a24dc313483cac6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030446"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>商務伺服器部署中 Skype Skype 連線能力

**摘要：** 了解如何與 Skype 消費者連線 Skype for Business Server。 也稱為 Skype 連線。
  
本文會逐步完成 Skype 連線的部署。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>適用於 IT 專業人員的 Skype 連線概觀

Skype 連線提供的功能來搜尋並加入 Skype 使用者的商務使用者 Skype。 Skype 連線是可讓您啟用同盟和目錄搜尋與 Skype 使用者的商務用 Skype 的功能。 啟用 Skype 連線後您 Skype for Business 使用者將能夠搜尋並加入 Skype 使用者。
  
## <a name="skype-directory-search"></a>Skype 目錄搜尋

Skype 目錄搜尋功能提供 Skype 商務使用者搜尋 Skype 連絡人的能力。 搜尋功能可讓使用者使用下列搜尋：
  
- **依顯示名稱，範例 「 John Doe 「 搜尋**-這無法傳回多結果，所以您可能無法找到您要尋找的。
    
- **依顯示名稱加上的位置，範例 「 John Doe 中巴塞隆納 「 搜尋**-這會縮小搜尋結果大幅。
    
- **透過電子郵件，範例 「 johndoe@outlook.com 「 搜尋**-這應該在大多數情況下，會傳回一個結果完全符合指定的電子郵件的其中一個。 但與多個帳戶相關聯的相同的電子郵件時，可能會傳回多個結果。
    
- **依電話號碼，範例 「 123-123-1234 「 搜尋**-這應該在大多數情況下，會傳回一個結果一個確實符合指定的電話。 電話號碼必須包含國碼/地區碼 (亦即 1-xxx-yyy-zzzz)。 與多個帳戶相關聯的相同的電話號碼時，可能會傳回多個結果。
    
- **Skype 名稱範例 「 JohnDoe1456 「 搜尋**-如果找到完全相符，它會傳回為第一個結果。 其他可能 「 名稱 」 相符項目可能會傳回。
    
    > [!NOTE]
    > Skype 目錄搜尋必須能夠彼此通訊連接埠 443 上的下列 IP 位址： 104.40.75.246、 23.101.135.34，以及 40.113.86.19。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>支援的部署矩陣 Skype 目錄搜尋

下表說明支援的 Skype 目錄搜尋。
  

||**Skype for Business Server 前端**|**Lync Server 2013 （或更舊版本） 前端**|**Comments**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge  <br/> |支援  <br/> |不支援  <br/> |Skype for Business Server 和 Edge 是 Skype 目錄搜尋的必要條件  <br/> |
|Skype 商務 Server Edge + Lync Server 2013 Edge 部署並排顯示  <br/> |支援  <br/> |不支援  <br/> |Skype 目錄搜尋流量會經由 Skype 商務伺服器 Edge server。 同盟流量會通過 edge 由系統管理員設定。 例如，系統管理員可以選擇繼續傳送到 Lync Server 2013 Edge server，哪些不支援 Skype 目錄搜尋的同盟流量。  <br/> |
|Lync Server 2013 （或更舊版本） Edge  <br/> |不支援  <br/> |不支援  <br/> ||
   
> [!NOTE]
> Skype for Business Server 前端所執行的 Addressbook 服務找到 Edge 的 Edge server 中的 Skype 搜尋連接埠 4443 存在。 
  
> [!NOTE]
> 以防客戶有多個網站在其內部部署中，而且如果他們已部署只有一個 Skype for Business Server Edge server/集區]，然後搜尋從所有網站的流量會通過單一可用的 Edge server。 管理員必須確定從所有網站的集區可以存取已部署的 Skype for Business Server Edge server 集區。 
  
> [!NOTE]
> Skype graph 服務會要求率超過 15 要求節流搜尋要求從任何內部部署或 Office 365 客戶/秒。 
  
> [!NOTE]
> 對於大型企業內部部署客戶，網域必須設為允許清單與 Skype 搜尋服務，以允許更高的要求速率。 
  
> [!NOTE]
> Skype 商務 Server 將調節傳入的要求，，如果在佇列中有太多暫止的要求。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>用於商務用 Skype Online 在 Office 365 部署的 Skype 連線

Skype 連線也是商務用 Skype 商務 Online，也就是 Office 365 的一部分的功能。 您可以在啟用 Skype 連線功能從 Skype for Business 系統管理中心內的 Office 365 入口網站。
  
Office 365 中型企業版、 Office 365 企業版、 Office 365 教育版，和 Office 365 for Government： 登入 Office 365 入口網站，並瀏覽至 Skype for Business 系統管理中心。 移至外部通訊。 在 [公用 IM 服務提供者] 下按一下 [啟用]。 如果您想要控制個別使用者的存取權 Skype 連線，您可以藉由編輯個別使用者的外部通訊設定來執行此動作。
  
針對 Office 365 小型企業進階版： 登入 Office 365，並移至系統\>服務設定\>立即訊息、 會議及會議。 開啟外部通訊。 功能變數的外部通訊參數會開啟 Skype 連線和與其他使用商務用 Skype 的組織的通訊。
  
如需 Skype 商務 Online 系統管理，請參閱：
  
- [允許使用者連絡外部商務用 Skype 使用者](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [嘗試如果不行 IM Skype for Business 或 Skype 外部連絡人項目](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [在商務用 Skype 中新增連絡人](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [系統管理員： 設定 Skype 針對個別使用者的企業設定](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Skype for Business Server 部署 Skype 連線

Skype 商務 Server 使用同盟存取架構可支援用 Skype 的連線。 此連線可以讓您 Skype for Business Server 使用者加入 Skype。 Skype 用戶端也可以將 Skype 新增至其連絡人清單的商務使用者。 根據使用者將能夠使用立即訊息通訊的企業伺服器 skype 行政規定必須設定的原則，請參閱彼此的目前狀態、 和起始音訊和視訊通話。 Skype 連線也是商務用 Skype 線上商務功能，可以啟用 skype 線上商務用 Skype 從客戶 for 商務版系統管理中心內的 Office 365 入口網站。
  
> [!NOTE]
> Skype for Business 伺服器已設定為使用公用立即訊息連線 (PIC) 與 Windows Messenger 連線時，如果您的部署已設定的 Skype 連線。 您可能要考慮的唯一變更是重新命名為 Skype 您現有 Messenger PIC 項目。 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Skype for Business Server 公用 IM 連線佈建網站已不再提供

先前用來以手動方式佈建商務用 Skype 之間的同盟關係的網站在內部部署和 Skype 不再需要將會關閉 8/15/2019年上。 與 Skype 同盟現在使用同盟協力廠商探索，也就是相同的機制所需同盟與 Skype for Business Online。

現在商務版部署任何內部部署商務用 Skype 和 Skype 使用者透過現有的公用 IM 基礎結構之間通訊需要與 Skype for Business Online 相容的內部部署 Edge Server 組態。

> [!NOTE]
> 大部分的客戶，包括商務用 Skype 同盟的所有部署所不需執行任何動作。
  
在內部部署，才能發佈它們主控每個網域同盟 DNS SRV 記錄。 使用[DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)規劃指引。 每個網域必須解決滿足最上層的後置詞的 FQDN 相符之網域的 DNS SRV 查詢至 edge server。 例如，假設網域 「 contoso.com 」:

|**有效的 Fqdn**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |在每個案例中，正確的 FQDN 必須出現在 SN 或 edge server 上所安裝的外部憑證的 SAN。   |
|access.contoso.com   ||
|**不正確的 Fqdn**|**原因**|
|sip.contoso edge.com   |沒有後置詞相符項目。  |
|sip.it.contoso.com   |不是最上層的後置字元符合。   |

[憑證](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)規劃可以找到有關外部憑證的進一步指引。

#### <a name="faqs"></a>常見問題集

**為什麼要佈建網站正在關閉？**
公用 IM (PIC) 佈建在 2006年中已部署的機制 (pic.lync.com) 已不再 scalability，就會關閉 8/15/2019年上。 相反地，公用 IM 同盟將會採用相同同盟所使用的模型由 Skype 商務線上，又稱為 「 夥伴探索 」，在內部部署是公開可被探索到由其同盟 DNS SRV 記錄:。

**這項變更意思公用 IM 同盟已被取代？**
否。 公用 IM 同盟會繼續受到支援許多年，可能等到商務用 Skype 內部部署產品達到週期結束。

**我們的公司具有混合關係 （共用的位址空間） 與 Skype for Business Online，我們會影響？**
否，因為您已同盟與 Skype for Business Online，這項變更不會影響您。
 
**這項變更意思我們的公司已啟用商務用 Skype 同盟？**
否。 如果您的 edge 伺服器 proxy 設定不啟用同盟與 Skype for Business Online 的主機服務提供者 (sipfed.online.lync.com) 然後這項變更不會影響的。 不過，相同的 DNS 和憑證需求，適用於同盟與 Skype for Business Online 現在也適用於同盟與 Skype 使用者。
 
**我們的公司很大，且無法變更因法規/規範/等原因而其 edge 設定...]我們可以做什麼？**
無法變更其 edge server 的組態為指定之任何內部部署組織應該連絡產品支援服務儘快。

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>啟用同盟和公共 IM 連線 (PIC)

專注在 Skype for Business Server 環境與設定 Skype 連線所需的管理工作。 在這個部分，我們假設管理員已部署 Skype for Business Server 並設定外部存取，也就是 Edge server。 
  
有需要，才能啟用同盟和 PIC 的三個主要步驟。 例如：
  
1. 設定同盟和 PIC
    
2. 設定至少一個原則以支援同盟的使用者存取
    
3. 設定設定 Skype PIC 提供者
    
#### <a name="1-configure-federation-and-pic"></a>1.設定同盟和 PIC

若要啟用 Skype 使用者能夠與 Skype for 貴組織中的商務使用者需要同盟。 公用立即訊息連線 (PIC) 是一種類別的同盟，以及它必須設定為啟用您的 Skype 商務版使用者 Skype 使用者進行通訊。 同盟和 PIC 已藉由使用 Skype for Business Server Control Panel。
  
> [!NOTE]
> PIC 的同盟已不再支援的產品版本之前 Lync Server 2010 ([Office Communications Server 中的 [即時通訊伺服器）。 支援的平台 PIC 同盟包含 Skype 商務伺服器、 Lync Server 2013 和 Lync Server 2010。 
  
若要啟用 Skype 使用者能夠與 Skype for 貴組織中的商務使用者需要同盟。 公用立即訊息連線 (PIC) 是一種類別的同盟，且它必須經過設定若要啟用 Skype 使用者進行通訊您 Skype for Business Server 使用者。 同盟和 PIC 會透過設定 Edge 設定] 對話方塊的 Skype for Business Server Control Panel 圖所示。
  
![定義新的 Edge 集區](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> EnableSkypeIdRouting 和 EnableSkypeDirectorySearch 屬性必須設為在才能搜尋的公用提供者設定 （請參閱更新版本的指示），則為 true。 
  
如此就完成必須在伺服器執行的管理工作。 現在您設定的 Skype 連線。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2.設定至少一個原則以支援同盟的使用者存取

使用 Skype for Business Server Control Panel，系統管理員必須設定一或多個外部使用者存取原則，以控制是否 Skype 使用者可以與內部 Skype for Business Server 使用者共同作業。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3.設定 Skype PIC 提供者設定

使用 Skype for Business Server 管理命令介面，系統管理員必須設定商務用 Skype 商務用戶端原則來顯示 Skype 作為其他 PIC 提供者。 
  
> [!NOTE]
> 公用立即訊息連線 (PIC) 服務提供者的使用者無法參加以 IM 或會議組織中的，直到您也支援公用 IM 連線設定至少一個原則 （步驟 2 中，此程序中更早版本）。 
  
新安裝您可以藉由啟用 Skype 公用提供者使用 Skype for Business Server Control Panel 圖所示設定 Skype 連線。
  
![SIP 同盟提供者](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> 若要升級至 Skype for Business Server 時，設定 Skype 連線您必須移除並重新加入現有的 Skype 公用提供者。 
  
設定 Skype 連線也可完成使用 PowerShell。 若要設定使用 PowerShell 的 Skype 連線：
  
1. 從 Skype for Business Server 前端伺服器中，開啟 Skype for Business Server 管理命令介面。
    
2. 執行下列兩個命令：
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 如果您在環境中還沒有 PIC 提供者，並建立新的 PIC 提供者然後您不需要執行移除 CsPublicProvider 指令程式。 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    較不明顯參數可以做什麼？
    
   - ProxyFqdn： 邊緣位置 Skype 同盟 （擁有/維護 microsoft）
    
   - IconURL： 圖示由 Lync&amp;用來以視覺方式識別 Skype 連絡人
    
   - NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList： 設定這些設定可讓使用者輸入 Skype 使用者 MSAs 而不需要了解 「 裝飾 」 與 「 msn.com 「 非 Microsoft 網域。 這就不用輸入 「 使用者 (contoso.com) @msn.com 「 不在 ExcludedDomainList 中的所有網域。 如果網域不在 [排除清單中，[MSA 會自動設定格式 SfB 用戶端。 我們已將最常見的 Microsoft 帳戶網域加入排除清單。
    
     > [!NOTE]
     > 公用提供者必須移除，而且如果變更新加入。 允許沒有就地變更。 
  
     > [!NOTE]
     > 在 Lync Server 2013 CU5 中新增&amp;Lync 桌面用戶端的 Office 2013 SP1、 NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改善其中加入 Skype 連絡人所需的 Lync 使用者 「 裝飾 」 以找出並將它們路由傳送到 Skype 非 Microsoft 網域的情況 (格式為： user(contoso.com)@msn.com)。 這些新的設定將允許的地址使用者的自動格式設定的對話方塊中輸入 「 新增 Skype 連絡人 」 與 NameDecorationRoutingDomain （這應設為 msn.com） 如果它不含 NameDecorationExcludedDomainList （中的網域我們目前可支援 msn.com、 live.com、 Hotmail.com、 outlook.com）。 
  
3. 從商務用 Skype 用戶端使用者現在可以搜尋並加入 Skype 使用者。
    
## <a name="clients-and-interoperability-matrix"></a>用戶端和互通性矩陣

下表概述 interop 最新版的 Skype 消費者和商務用 Skype 的最新版本之間的狀態。
  

|**Skype 用戶端**|**新增連絡人、 IM、 目前狀態、 音訊及視訊通話**|**Comment**|
|:-----|:-----|:-----|
|Skype Windows 桌面  <br/> |7.6 或更高版本、 Windows XP 和更高版本  <br/> |**新增**： 新增支援在 Windows XP 和 Windows Vista **（需要最新的用戶端版本 7.26 或更高版本）** 上執行的 Windows 用 Skype 用戶端 <br/> |
|Skype 行動裝置-Android 手機和平板電腦  <br/> |6.19 或更新版本，執行 Android 作業系統版本 4.0.3 或更高層級  <br/> |低規格裝置可能不支援視訊通話  <br/> |
|Skype 行動裝置-iOS  <br/> |6.11 或更新版本，在 IOS 7 或更高版本  <br/> |不支援已 4th 產生 iPhone 4 和更早版本、 iPod 和更早，iPad 1st 產生  <br/> |
|Skype Mac  <br/> |7.19 或更新版本，在 Mac OS X 10.9 (Mavericks) 或更高版本  <br/> |需要 Mac OSX 「 10.9 或更高版本  <br/> |
|Skype Universal Windows 應用程式 (Windows 10) 桌面和行動裝置  <br/> |Windows 10 (Redstone 1 更新或更新版本)  <br/> |Windows 通用應用程式會在新增 interop 支援 Fall 2016 收到更新  <br/> |
   
下表概述 interop 最新版的商務用 Skype 和 Skype 消費者的最新版本之間的狀態。 
  
|**用戶端**|**Skype 目錄搜尋，並新增連絡人**|**Skype A / V，IM interop**|
|:-----|:-----|:-----|
|商務用 Skype  <br/> |是  <br/> |是  <br/> |
|Mac 版商務用 Skype  <br/> |可以新增 （沒有搜尋）  <br/> |是  <br/> |
|Lync Desktop 2013  <br/> |可以新增 （沒有搜尋）  <br/> |是  <br/> |
|Lync Web App 的線上和內部部署  <br/> |不適用  <br/> |不適用  <br/> |
|Lync 行動裝置-Windows Phone  <br/> |即將推出  <br/> |是  <br/> |
|Lync 行動裝置-Android  <br/> |即將推出  <br/> |是  <br/> |
|Lync 行動裝置-iOS  <br/> |即將推出  <br/> |是  <br/> |
|Lync Room System  <br/> |即將推出  <br/> |是  <br/> |
|Lync 現代化應用程式 (Win 8.1)  <br/> |是  <br/> |是  <br/> |
|Lync Mac 2011  <br/> |可以新增 （沒有搜尋）  <br/> |是  <br/> |
|Lync 桌面 2010  <br/> |可以新增 （沒有搜尋）  <br/> |是  <br/> |
|Lync Phone Edition  <br/> |不適用  <br/> |不適用  <br/> |
|Lync Attendant  <br/> |不適用  <br/> |不適用  <br/> |
   

