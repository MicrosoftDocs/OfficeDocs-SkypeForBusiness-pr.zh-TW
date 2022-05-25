---
title: 在 商務用 Skype Server 中部署Skype連線能力
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 摘要：瞭解如何將商務用 Skype Server與Skype取用者連線。 也稱為Skype連線。
ms.openlocfilehash: 6e569a52569e72d2fe67bdde786b752834452069
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671679"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>在 商務用 Skype Server 中部署Skype連線能力

**總結：** 瞭解如何將商務用 Skype Server與Skype取用者連線。 也稱為Skype連線。
  
本文將逐步解說Skype連線能力的部署。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>適用于 IT 專業人員Skype連線概觀

Skype連線能力可讓商務用 Skype使用者搜尋和新增Skype使用者。 Skype連線能力是商務用 Skype功能，可讓您啟用與Skype使用者的同盟和目錄搜尋。 啟用Skype連線之後，商務用 Skype使用者將能夠搜尋並新增Skype使用者。
  
## <a name="skype-directory-search"></a>Skype目錄搜尋

Skype目錄搜尋功能可讓商務用 Skype使用者搜尋Skype連絡人。 搜尋功能可讓使用者使用下列專案進行搜尋：
  
- **依顯示名稱搜尋，例如 「John Doe」** - 這可能會傳回許多結果，因此您可能找不到要尋找的內容。
    
- **依顯示名稱加上位置搜尋，例如「John Doe in Marketplace」** - 這會大幅縮小搜尋結果的範圍。
    
- **依電子郵件搜尋，例如「johndoe@outlook.com」** - 這應該會在大部分情況下傳回一個結果;完全符合指定電子郵件的 。 但是，如果相同的電子郵件與多個帳戶相關聯，則可能會傳回多個結果。
    
- **依電話號碼搜尋，例如 「123-123-1234」** - 這應該會在大部分情況下傳回一個結果;完全符合指定手機的 。 電話數位必須包含國家/地區代碼 (也就是 1-xxx-yyy-zzzz) 。 如果相同的電話號碼與多個帳戶相關聯，則可能會傳回多個結果。
    
- **依Skype名稱、範例 「JohnDoe1456」** 搜尋 - 如果找到完全相符的專案，則會傳回為第一個結果。 可能會傳回其他可能的「名稱」相符專案。
    
    > [!NOTE]
    > Skype目錄搜尋必須能夠與埠 443 上的下列 IP 位址通訊：104.40.75.246、23.101.135.34 和 40.113.86.19。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>支援Skype目錄搜尋的部署矩陣

下表概述Skype目錄搜尋的支援。
  

|&nbsp;|商務用 Skype Server前端|Lync Server 2013 (或較舊) 前端|註解|
|:-----|:-----|:-----|:-----|
|商務用 Skype Server Edge   |支援   |不支援   |商務用 Skype Server和 Edge 是Skype目錄搜尋的必要條件   |
|商務用 Skype Server Edge + Lync Server 2013 Edge 並存部署   |支援   |不支援   |Skype目錄搜尋流量流經商務用 Skype Server Edge 伺服器。 同盟流量會通過系統管理員所設定的邊緣。 例如，系統管理員可以選擇繼續透過不支援 Skype Directory 搜尋的 Lync Server 2013 Edge 伺服器傳送同盟流量。   |
|Lync Server 2013 (或舊版) Edge   |不支援   |不支援   ||
   
> [!NOTE]
> 在商務用 Skype Server前端執行的通訊錄服務會根據 Edge 伺服器中Skype搜尋埠 4443 的存在來尋找 Edge。 
  
> [!NOTE]
> 如果客戶在其內部部署中有多個月臺，而且只要部署一個商務用 Skype Server Edge 伺服器/集區，則來自所有網站的搜尋流量將會通過單一可用的 Edge 伺服器。 系統管理員必須確定來自所有網站的集區可以存取已部署商務用 Skype Server Edge 伺服器/集區。 
  
> [!NOTE]
> Skype圖形服務會針對來自任何內部部署或Microsoft 365或Office 365客戶的搜尋要求進行節流，如果要求速率超過 15 個要求/秒。 
  
> [!NOTE]
> 對於大型企業內部部署客戶，必須將網域新增至具有Skype搜尋服務的允許清單，以允許更高的要求率。
  
> [!NOTE]
> 如果佇列中有太多擱置中的要求，商務用 Skype Server將會節流傳入要求。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>部署 商務用 Skype Online 的Skype連線能力

Skype連線能力也是 商務用 Skype Online 的功能，這是Microsoft 365和Office 365的一部分。 您可以從 Microsoft 365 系統管理中心 內的 商務用 Skype 管理中心啟用Skype連線功能。
  
針對 Microsoft 365 Midsize Business、Office 365 企業版、Microsoft 365 教育版 及 Office 365：登入Microsoft 365 系統管理中心並流覽至商務用 Skype系統管理中心。 移至 [外部通訊]。 在 [公用 IM 服務提供者] 底下，按一下 [啟用]。 如果您想要控制個別使用者對連線Skype存取權，您可以編輯個別使用者的外部通訊設定來執行此動作。
  
如需Office 365 Small Business Premium：登入Office 365，然後移至 管理員 \> Service 設定 \> 立即訊息、會議和會議。 開啟外部通訊。 外部通訊交換器會開啟Skype連線能力，以及與其他使用商務用 Skype的組織通訊。
  
如需 商務用 Skype Online 管理的詳細資訊，請參閱：
  
- [允許使用者連絡外部商務用 Skype 使用者](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [如果無法 IM 商務用 Skype或Skype外部連絡人，該怎麼辦](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [在 商務用 Skype 中新增連絡人](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [系統管理員：為個別使用者設定商務用 Skype設定](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>部署 Skype 連線商務用 Skype Server

商務用 Skype Server使用同盟存取架構來支援與 Skype 的連線。 此連線可讓您的商務用 Skype Server使用者新增Skype。 Skype用戶端也可以將商務用 Skype使用者新增至其連絡人清單。 根據系統管理設定的原則商務用 Skype Server使用者將能夠使用立即訊息進行通訊、查看彼此的目前狀態，以及起始音訊和視訊通話。 Skype連線能力也是 商務用 Skype Online 的一項功能，可從 Microsoft 365 系統管理中心 內的 商務用 Skype 系統管理中心為 商務用 Skype Online 客戶啟用。
  
> [!NOTE]
> 如果商務用 Skype Server已設定為使用 PUBLIC Instant Messaging Connectivity 與 Windows Messenger 連線 (PIC) ，則您的部署已設定為Skype連線。 您可能要考慮的唯一變更是將現有的 Messenger PIC 專案重新命名為 Skype。 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>商務用 Skype Server公用 IM 連線布建網站已無法再使用

先前用來在商務用 Skype內部部署與Skype之間手動布建同盟的月臺已不再需要，而且將會在 2019/8/15 關閉。 與Skype同盟現在會利用同盟夥伴探索，這是與 商務用 Skype Online 同盟所需的相同機制。

任何內部部署商務用 Skype部署與透過現有公用 IM 基礎結構Skype使用者之間的通訊，現在需要內部部署 Edge Server 組態與 商務用 Skype Online 相容。

> [!NOTE]
> 大部分的客戶都不需要採取任何動作，包括與 商務用 Skype Online 同盟的所有部署。
  
需要內部部署，才能針對其裝載的每個網域發佈同盟 DNS SRV 記錄。 [DNS 規劃](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)中有提供指引。 每個網域都必須透過 DNS SRV 查詢解析為符合網域最上層尾碼的邊緣伺服器 FQDN。 例如，假設網域為 「contoso.com」：

|**有效的 FQDN**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |在每個案例中，確切的 FQDN 必須存在於邊緣伺服器上所安裝外部憑證的 SN 或 SAN 中。   |
|access.contoso.com   ||
|**不正確 FQDN**|**原因**|
|sip.contoso-edge.com   |不是尾碼相符專案。  |
|sip.it.contoso.com   |不是最上層尾碼相符專案。   |

如需外部憑證的進一步指引，請參閱 [憑證規劃](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)。

#### <a name="faqs"></a>常見問題集

**為何要關閉布建網站？**
2006 年部署的公用 IM (PIC) 布建機制 (pic.lync.com) 已無法再提供服務，且將于 2019/8/15 關閉。 相反地，公用 IM 同盟會假設 商務用 Skype Online 所使用的同盟模型相同，稱為「夥伴探索」，因此內部部署可由其同盟 DNS SRV 記錄 (的) 公開探索。

**這項變更是否表示公用 IM 同盟已被取代？**
不能。 公用 IM 同盟將持續支援許多年，可能直到商務用 Skype內部部署產品達到生命週期結束為止。

**我們公司與 商務用 Skype Online) 共用位址空間 (混合式關聯性，我們是否會受到影響？**
否，因為您已經與 商務用 Skype Online 同盟，所以這項變更不會影響您。
 
**這項變更是否表示我們的公司必須啟用與 商務用 Skype Online 的同盟？**
不能。 如果您的邊緣伺服器 Proxy 設定未啟用與 商務用 Skype Online 主機提供者同盟 (sipfed.online.lync.com) 則這項變更不會影響該項。 不過，套用至與 商務用 Skype Online 同盟的相同 DNS 和憑證需求現在也適用于與Skype使用者同盟。
 
**我們的公司很大，因法規/合規性/等原因而無法變更其邊緣設定...我們可以做什麼？**
任何無法依指定變更其 Edge Server 設定的內部部署組織，都應該儘早連絡產品支援人員。

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>啟用同盟和公用 IM 連線 (PIC) 

現在將焦點放在設定連線Skype所需的商務用 Skype Server環境和管理工作。 在本節中，我們假設系統管理員已部署商務用 Skype Server並設定外部存取，也稱為 Edge 伺服器。 
  
啟用同盟和 PIC 需要三個主要步驟。 例如：
  
1. 設定同盟和 PIC
    
2. 設定至少一個原則以支援同盟使用者存取
    
3. 設定 Skype PIC 提供者設定
    
#### <a name="1-configure-federation-and-pic"></a>1.設定同盟和 PIC

需要同盟才能讓Skype使用者與組織中的商務用 Skype使用者通訊。 PUBLIC Instant Messaging Connectivity (PIC) 是同盟的類別，而且必須設定為讓商務用 Skype使用者與Skype使用者通訊。 同盟和 PIC 是使用 商務用 Skype Server 主控台來設定。
  
> [!NOTE]
> Lync Server 2010 (Live Communication Server Office Communications Server) 之前的產品版本不再支援 PIC 同盟。 PIC 同盟支援的平臺包括 商務用 Skype Server、Lync Server 2013 和 Lync Server 2010。 
  
需要同盟才能讓Skype使用者與組織中的商務用 Skype使用者通訊。 PUBLIC Instant Messaging Connectivity (PIC) 是同盟的類別，而且必須設定為讓商務用 Skype Server使用者與Skype使用者通訊。 同盟和 PIC 是使用商務用 Skype Server 主控台的 [Edge 組態] 對話方塊來設定，如圖所示。
  
![定義新的 Edge 集區。](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 在公用提供者設定中，EnableSkypeIdRouting 和 EnableSkypeDirectorySearch 屬性必須設定為 true， (請參閱後續) 搜尋工作的指示。 
  
這會完成必須在伺服器上執行的系統管理工作。 您現在已設定Skype連線能力。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2.設定至少一個原則以支援同盟使用者存取

使用商務用 Skype Server 主控台，系統管理員必須設定一或多個外部使用者存取原則，以控制Skype使用者是否可以與內部商務用 Skype Server使用者共同作業。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3.設定 Skype PIC 提供者設定

使用 商務用 Skype Server 管理命令介面，系統管理員必須設定商務用 Skype用戶端原則，以將Skype顯示為其他 PIC 提供者。 
  
> [!NOTE]
> 公用立即訊息連線 (PIC) 服務提供者的使用者無法參與組織中的 IM 或會議，直到您也在此程式稍早的步驟 2 設定至少一個原則 (，) 支援公用 IM 連線。 
  
針對新的安裝，您可以使用商務用 Skype Server 主控台來啟用Skype公用提供者，以設定Skype連線能力，如圖所示。
  
![SIP 同盟提供者。](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> 若要在升級至 商務用 Skype Server 時設定Skype連線能力，您必須移除並重新新增現有的Skype公用提供者。 
  
設定Skype連線能力也只能使用 PowerShell 來完成。 若要使用 PowerShell 設定Skype連線：
  
1. 從商務用 Skype Server前端伺服器，開啟 [商務用 Skype Server 管理命令介面]。
    
2. 執行下列兩個命令：
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 如果您的環境中還沒有 PIC 提供者，而且正在建立新的 PIC 提供者，則不需要執行Remove-CsPublicProvider Cmdlet。 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    較不明顯的參數有何用途？
    
   - ProxyFqdn：Skype同盟邊緣 (由 Microsoft) 擁有/維護的位置
    
   - IconURL：Lync &amp; 商務用 Skype用戶端用來以視覺化方式識別Skype連絡人的圖示
    
   - NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList：設定這些專案可讓使用者輸入Skype使用者的 MSA，而不需要知道如何使用 「msn.com」 來「裝飾」非 Microsoft 網域。 這樣就不需要針對不在 ExcludedDomainList 中的所有網域輸入「使用者 (contoso.com) @msn.com」。 如果網域不在 [排除] 清單中，SfB 用戶端會自動格式化 MSA。 我們已將最常見的 Microsoft 帳戶網域新增至排除清單。
    
     > [!NOTE]
     > 如果進行變更，則必須移除公用提供者並新增。 不允許就地變更。 
  
     > [!NOTE]
     > 在 2013 SP1 Office Lync Server 2013 CU5 &amp; Lync 桌面用戶端中新增的 NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 可改善 Lync 使用者新增Skype連絡人以「裝飾」非 Microsoft 網域，以識別並路由傳送至Skype (：使用者 (contoso.com) @msn.com) 格式的情況。 這些新設定可讓使用者在 [新增Skype連絡人] 對話方塊中輸入的位址自動格式化，其中包含 NameDecorationRoutingDomain (，如果 NameDecorationExcludedDomainList 中沒有包含網域，則應該設定為 msn.com) ， (我們目前可以支援 msn.com、live.com、Hotmail.com、outlook.com) 。 
  
3. 從商務用 Skype用戶端使用者現在可以搜尋並新增Skype使用者。
    
## <a name="clients-and-interoperability-matrix"></a>用戶端和互通性矩陣

下表概述最新版Skype取用者與最新版商務用 Skype之間的互通性狀態。
  

|Skype用戶端|新增連絡人、IM、目前狀態、音訊和視訊通話|留言|
|:-----|:-----|:-----|
|Skype Windows桌面   |7.6 或更高版本，Windows XP 和更新版本   |**新增**：針對在 Windows XP 上執行的Windows Skype用戶端新增支援，而 Windows Vista **(需要最新的用戶端 7.26 版或更新版本)**  |
|Skype行動裝置版 - Android 電話和 Tablet   |6.19 或更新版本，執行 Android OS 4.0.3 版或更新版本   |低規格裝置可能不支援視訊通話   |
|Skype Mobile - iOS   |IOS 7 或更新版本上的 6.11 或更高版本   |不支援 iPhone 4 和更早版本、iPod 第 4 代和更早版本，iPad第 1 代   |
|Skype Mac   |7.19 或更新版本，Mac OS X 10.9 (或更新版本的) 或更高版本   |需要 Mac OSX 10.9 或更新版本   |
|Skype通用Windows應用程式 (Windows 10) 桌面和行動裝置版   |Windows 10 (Redstone 1 更新或更新版本)    |Windows通用應用程式將在 2016 年秋季收到更新，並新增 Interop 支援   |
   
下表概述最新版商務用 Skype與最新版Skype取用者之間的互通性狀態。 
  
|用戶端|Skype目錄搜尋和新增連絡人|Skype A/V、IM Interop|
|:-----|:-----|:-----|
|商務用 Skype   |是   |是   |
|Mac 版商務用 Skype   |無法新增 (搜尋)    |是   |
|Lync Desktop 2013   |無法新增 (搜尋)    |是   |
|Lync Web 應用程式 - 線上和內部部署   |不適用   |不適用   |
|Lync Mobile - Windows Phone   |即將推出   |是   |
|Lync Mobile - Android   |即將推出   |是   |
|Lync Mobile - iOS   |即將推出   |是   |
|Lync Room System   |即將推出   |是   |
|Lync Modern App (Win 8.1)    |是   |是   |
|Lync Mac 2011   |無法新增 (搜尋)    |是   |
|Lync Desktop 2010   |無法新增 (搜尋)    |是   |
|Lync Phone Edition   |不適用   |不適用   |
|Lync Attendant   |不適用   |不適用   |
   
