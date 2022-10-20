---
title: 設定會話框線控制器 - 多個租使用者
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何設定一個會話框線控制器 (SBC) ，為 Microsoft 合作夥伴和/或 PSTN 電信業者提供多個租使用者服務。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3789270bc9826c11dee338b5221bc019191f50f2
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614406"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>設定多個租用戶的工作階段邊界控制器

直接路由支援設定一個會話框線控制器 (SBC) 以服務多個租使用者。

> [!NOTE]
> 此案例是專為本檔稍後提到的 Microsoft 合作夥伴和/或 PSTN 電信業者所設計。 電信業者銷售傳送給 Microsoft Teams 給客戶的電話語音服務。 

電信業者：
-  (客戶不需要實作 SBC，即可在其資料中心部署及管理 SBC，且會從 Teams 用戶端) 中的電信業者接收電話語音服務。
- 將 SBC 與多個租使用者相互連接。
- 提供公用交換電話網路 (PSTN) 服務給客戶。
- 管理結束通話品質。
- PSTN 服務需另行收費。

Microsoft 不會管理電信業者。 Microsoft 提供電話系統—私人 Exchange (PBX) ，以及 Teams 用戶端。 Microsoft 也會認證手機，並認證可搭配手機系統使用的 SBC。 選擇電信業者之前，請先確定您的選擇有經過認證的 SBC，而且可以管理端對尾的語音品質。

以下是設定案例的技術實作步驟。

**僅限電信業者：**
1. 根據認證 SBC 廠商的指示，部署 [SBC](#deploy-and-configure-the-sbc)並設定代管案例。
2. 在電信業者租使用者中註冊基本功能變數名稱，並要求萬用字元憑證。
3. 為每個客戶註冊子域，這是基礎網域的一部分。

**由客戶全域系統管理員身分執行的電信業者：**
1. 將子功能變數名稱稱新增至客戶租使用者。
2. 啟用子功能變數名稱稱。
3. 設定從電信業者到客戶租使用者的主幹，並布建使用者。

*請確定您瞭解 DNS 基本概念，以及如何在 Microsoft 365 中管理功能變數名稱。請參閱 [取得 Microsoft 365 網域的說明，](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) 然後再繼續進行。*

## <a name="deploy-and-configure-the-sbc"></a>部署和設定 SBC

如需如何針對 SBC 主機服務案例部署和設定 SBC 的詳細步驟，請參閱 SBC 廠商的檔。

- **AudioCodes：** 如需 SBC 主機服務案例的設定，請參閱 [直接路由設定附注](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams) ，如「將 AudioCodes SBC 連線到 Microsoft Teams 直接路由主機模式設定注意事項」中所述。 
- **甲骨文：** 如一節所述，請參閱 SBC 主機服務案例設定的 [直接路由設定附注](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html) 。 
- **功能區通訊：** 如需如何設定功能區核心系列 SBC 的檔，請參閱 [功能區通訊 SBC Core Microsoft Teams 設定指南](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+MS+Teams+Solution+Guide) 。 另請參閱 [功能區最佳做法 - 設定 Microsoft Teams 直接路由 SBC Edge 的貨運公司](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems (任何節點) ：** 在 [TE-Systems 社群頁面網站上](https://community.te-systems.de/) 註冊，以取得如何為多個租使用者設定任何節點 SBC 的檔和範例。
- **元切換：** 在 [元切換社群頁面網站上](https://manuals.metaswitch.com/MAN39555) 註冊，以取得如何為多個租使用者啟用 Perimeta SBC 的檔。

> [!NOTE]
> 請確定您知道如何設定「連絡人」標頭。 連絡人標頭是用來在傳入的邀請訊息上尋找客戶租使用者。 

## <a name="register-a-base-domain-and-subdomains"></a>註冊基本網域和子域

針對主機服務案例，您需要建立：

- 由電信業者擁有的一個基本功能變數名稱。
- 子域是每個客戶租使用者中基本功能變數名稱的一部分。

在下列範例中：

- Adatum 是提供網際網路和電話語音服務，為多位客戶提供服務的電信業者。
- Woodgrove Bank、Contoso 和 Adventure Works 是三個擁有 Microsoft 365 網域但從 Adatum 接收電話語音服務的客戶。

子域 **必須** 符合客戶所設定之主幹的 FQDN 名稱，以及傳送邀請至 Microsoft 365 時連絡人標頭中的 FQDN 名稱。 

當來電送達 Microsoft 365 直接路由介面時，介面會使用連絡人標頭來尋找應查詢使用者的租使用者。 直接路由不會在 [邀請] 上使用電話號碼查閱，因為有些客戶的非 DID 號碼可能會與多個租使用者重迭。 因此，需要連絡人標頭中的 FQDN 名稱，才能識別確切的租使用者，才能依電話號碼查詢使用者。

*如需在 Microsoft 365 組織中建立功能變數名稱的詳細資訊，請參閱 [取得 Microsoft 365 網域的說明](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。*

下圖摘要列出基礎網域、子域和連絡人標頭的需求。

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="顯示網域和連絡人標頭需求的圖表。" lightbox="media/direct-routing-1-sbc-requirements.png":::

SBC 需要憑證才能驗證連線。 針對 SBC 主機服務案例，電信業者必須要求使用 CN 和/或 SAN *\* .base_domain (的憑證， \* 例如 .customers.adatum.biz)*。 此憑證可用來驗證從單一 SBC 服務之多個租使用者的連線。

下表是其中一個設定的範例。


|新的功能變數名稱 |類型|註冊  |憑證 CN/SAN for SBC  |範例中的租使用者預設網域  |傳送電話給使用者時，SBC 必須在連絡人標頭中顯示的 FQDN 名稱|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    基地     |     在電信業者租使用者中  |    \*.customers.adatum.biz  |   adatum.biz      |NA，這是服務租使用者，沒有使用者 |
|sbc1.customers.adatum.biz|    子域  |    在客戶租使用者中  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   子域 | 在客戶租使用者中   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   子域 | 在客戶租使用者中 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

若要設定基礎和子域，請遵循下列步驟。 此範例會針對 Woodgrove Bank 租使用者) 中的一個客戶 (sbc1.customers.adatum.biz 設定基本功能變數名稱 (customers.adatum.biz) 和子域。

> [!NOTE]
> 使用 sbcX.customers.adatum.biz 啟用電信業者租使用者中的語音;sbcX 可以是任何唯一且有效的英數位元主機名稱。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>在電信業者租使用者中註冊基本功能變數名稱

**這些動作會在電信業者租使用者中執行。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>確定您在電信業者租使用者中擁有適當的權利

您必須以全域系統管理員的身分登入Microsoft 365 系統管理中心，才能新增網域。 

若要驗證您擁有的角色，請登入Microsoft 365 系統管理中心 (https://portal.office.com) ，移至 **[使用者**  >  **作用中使用者**]，然後確認您擁有全域系統管理員角色。 

如需有關系統管理員角色以及如何在 Microsoft 365 中指派角色的詳細資訊，請參閱 [關於系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>將基本網域新增至租使用者並進行驗證

1. 在 [Microsoft 365 系統管理中心] 中，移至 **[設定**  >  **網域新增網**  >  **域]**。

2. 在 [ **輸入您擁有的網域** ] 方塊中，輸入基礎網域的 FQDN。 在下列範例中，基底網域 *為 customers.adatum.biz*。

3. 按一下 **[下一步]**。

4. 在此範例中，租使用者已經 adatum.biz 為已驗證的功能變數名稱。 精靈不會要求其他驗證，因為 customers.adatum.biz 是已註冊名稱的子域。 不過，如果您新增之前尚未驗證的 FQDN，則必須完成驗證程式。 請 [參閱下方](#add-a-subdomain-to-the-customer-tenant-and-verify-it)的驗證程式。

5. 選 **取 [下一步**]，然後在 [ **更新 DNS 設定** ] 頁面上，選取 [ **我要自己新增 DNS 記錄** ]，然後選取 [ **下一步]**。

6. 在下一頁中，清除 (的所有值，除非您想要使用 Exchange、SharePoint、Teams 或 商務用 Skype) 的功能變數名稱，選取 [**下一步**]，然後選取 [**完成]**。 確定您的新網域處於設定完成狀態。

### <a name="activate-the-domain-name"></a>啟用功能變數名稱

註冊功能變數名稱之後，您需要新增至少一個 Teams 授權使用者或資源帳戶來啟用該功能變數名稱。 可接受的帳戶將會使用下列其中一種 SKU 的授權：

- 含 Office 365 E1/E3/E5 或 Microsoft 365 E3/E5 的使用者帳戶。
- 具有 Office 365 A1/A3/A5 或 Microsoft 365 A1/A3/A5 的使用者帳戶。
- 含 Office 365 F3 或 Microsoft 365 F1/F3 的使用者帳戶。
- 含 G1/G3/G5 或 Microsoft 365 G3/G5 Office 365使用者帳戶。
- 具有Microsoft 365 商務基本版/標準/進階版的使用者帳戶。
- 具有通用區域電話的使用者帳戶。
- 具有 **Microsoft Teams 電話資源帳戶授權的資源帳戶**。

此外，帳戶的 UPN (使用者主體名稱) 或商務用 Skype內部部署 SIP 位址必須與新建立的網域使用相同的 FQDN。

如需在 Microsoft 365 組織中新增使用者的詳細資訊，請參閱 [取得 Microsoft 365 網域的說明](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。

例如：test@customers.adatum.biz

![基本網域啟用頁面的螢幕擷取畫面。](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>在客戶租使用者中註冊子功能變數名稱稱

您必須為每個客戶建立唯一的子功能變數名稱稱。 在此範例中，我們將在租使用者中建立具有預設功能變數名稱 woodgrovebank.us 的子域 sbc1.customers.adatum.biz。

**下列所有動作都位於客戶租使用者中。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>確定您在客戶租使用者中擁有適當的權利

您必須以全域系統管理員的身分登入Microsoft 365 系統管理中心，才能新增網域。 

若要驗證您擁有的角色，請登入Microsoft 365 系統管理中心 (https://portal.office.com) ，移至 **[使用者**  >  **作用中使用者**]，然後確認您擁有全域系統管理員角色。 

如需有關系統管理員角色以及如何在 Microsoft 365 中指派角色的詳細資訊，請參閱 [關於系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>新增子域至客戶租使用者並進行驗證

1. 在 [Microsoft 365 系統管理中心] 中，移至 **[設定**  >  **網域新增網**  >  **域]**。

2. 在 [ **輸入您擁有的網域** ] 方塊中，輸入此租使用者子域的 FQDN。 在下面的範例中，子域為 sbc1.customers.adatum.biz。

3. 選取 **[下一步]**。

4. FQDN 從未在租使用者中註冊過。 在下一個步驟中，您將需要驗證網域。 選 **取 [改為新增 TXT 記錄]**。 

5. 選 **取 [下一步**]，並記下產生的 TXT 值以驗證功能變數名稱。

    ![[驗證網域] 頁面上文字記錄的螢幕擷取畫面。](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 使用電信業者 DNS 主機服務提供者中前一個步驟的值建立 TXT 記錄。

    如需詳細資訊，請參閱 [在任何 DNS 主機服務提供者建立 DNS 記錄](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。

7. 移至客戶的Microsoft 365 系統管理中心，然後選取 **[驗證]**。 

8. 在下一頁中，選取 **[我要自己新增 DNS 記錄]，** 然後選取 [ **下一步]**。

9. 在 [**選擇您的線上服務** 頁面上，清除所有選項，然後選取 **[下一步]**。

10. 選取 **[更新 DNS 設定**] 頁面上的 [**完成**]。

11. 確定狀態已 **設定完成**。

    ![顯示安裝程式狀態的頁面螢幕擷取畫面。](media/direct-routing-12-sbc-setup-complete.png)

> [!NOTE]
> 個別用戶端的基底 URL 和子域必須位於相同的租使用者上，才能讓您新增 _直接路由主幹_ 。

### <a name="activate-the-subdomain-name"></a>啟用子功能變數名稱稱

註冊子功能變數名稱稱之後，您需要新增至少一個 Teams 授權使用者或資源帳戶來啟用它。 可接受的帳戶將會使用下列其中一種 SKU 的授權：

-   含 Office 365 E1/E3/E5/A3/A5 或 Microsoft 365 E3/E5/A3/A5 的使用者帳戶
-   含 Office 365 F1/F3 或 Microsoft 365 F1/F3 的使用者帳戶
-   含 Microsoft 365 商務基本版/標準/進階版和 G3/G5 方案的使用者帳戶
-   具有通用區域電話的使用者帳戶
-   具有Microsoft Teams 電話 **資源帳戶授權的資源帳戶**

此外，帳戶的 UPN (使用者主體名稱) 或商務用 Skype內部部署 SIP 位址必須與新建立的子域使用相同的 FQDN。

如需在 Microsoft 365 組織中新增使用者的詳細資訊，請參閱 [取得 Microsoft 365 的說明](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。

例如：test@sbc1.customers.adatum.biz

![啟用子域頁面的螢幕擷取畫面。](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>建立主幹和布建使用者

在初次發行直接路由時，Microsoft 需要使用New-CSOnlinePSTNGateway Cmdlet 將主幹新增至每個服務的租使用者 (客戶租使用者) 。

不過，此方法無法求出最佳的兩個原因：
 
- **管理負荷**。 例如，卸載或耗盡 SBC 會變更某些參數，例如啟用或停用媒體略過。 變更埠需要透過執行 Set-CSOnlinePSTNGateway) 來變更多個租使用者中的參數 (，但事實上卻是相同的 SBC。 

-  **負荷處理**。 收集和監控主幹健康情況資料： 從多個邏輯主幹收集的 SIP 選項，實際上是相同的 SBC 和相同的實體主幹，會減慢路由資料的處理速度。
 
根據此意見反應，Microsoft 將提供新的邏輯，為客戶租使用者布建主幹。

已引進兩個新實體：

- 在電信業者租使用者中註冊的承運業者主幹，使用命令 New-CSOnlinePSTNGateway。 例如： 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- 不需要註冊的衍生樹幹。 它只是從電信業者主幹中新增的所要主機名稱。 它會從電信業者主幹衍生出其所有組態參數。 與電信業者主幹的關聯是根據 FQDN 名稱 (請參閱下方) 的詳細資料。

**布建邏輯和範例**

- 貨運公司只需使用Set-CSOnlinePSTNGateway命令， (電信業者網域) 的承運業者主幹來設定和管理單一主幹。 在上述範例中，adatum.biz。

- 在客戶租使用者中，電信業者需要將衍生主幹 FQDN 新增至語音路由。 不需要為主幹執行New-CSOnlinePSTNGateway。

- 如名稱所示，衍生樹幹會繼承或衍生出電信業者主幹的所有組態參數。 

例子：
- Customers.adatum.biz – 必須在電信業者租使用者中建立的承運業者主幹。

- Sbc1.customers.adatum.biz – 客戶租使用者中的衍生主幹。 您可以在語音路由中新增客戶租使用者中衍生主幹的名稱，而不需建立。

- 承運業者必須設定 DNS 記錄，以解決衍生主幹 FQDN 到電信業者 SBC IP 位址的問題。

- 對承運業者租使用者) 上電信業者主幹 (所做的任何變更，都會自動套用至衍生主幹。 例如，貨運公司可以變更承運業者主幹上的 SIP 埠，而這項變更適用于所有衍生主幹。 設定主幹的新邏輯簡化了管理，因為您不需要移至每個租使用者並變更每個主幹上的參數。

- 選項只會傳送到電信業者主幹 FQDN。 承運業者主幹的健康情況會套用至所有衍生樹幹，並用於路由決策。 深入瞭解 [直接路由選項](./direct-routing-monitor-and-troubleshoot.md)。

- 承運業者可以耗盡承運業者主幹，而且也會耗盡所有衍生成的主幹。 
 
> [!NOTE]
> 套用至電信業者主幹的數位翻譯規則不適用於衍生主幹。 這是已知的問題。 另一個解決方案是，必須為每個客戶的租使用者建立數位翻譯規則。

**從先前的型號移轉到承運業者主幹**
 
若要從電信業者託管模型的目前實作移轉到新模型，貨運公司必須為客戶租使用者重新設定主幹。 使用Remove-CSOnlinePSTNGateway (從客戶租使用者移除主幹，離開電信業者租使用者的主幹) -

我們強烈建議儘快移轉到新解決方案，我們將使用電信業者和衍生主幹模型來加強監控和布建。
 
如需設定在連絡人標頭中傳送子域 FQDN 名稱的詳細資訊，請參閱 [SBC 廠商指示](#deploy-and-configure-the-sbc)。

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>設定多租使用者容錯移轉的考慮 

若要為多租使用者環境設定容錯移轉，您必須執行下列動作：

- 針對每個租使用者，新增兩種不同 SBC 的 FQDN。 例如：

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- 在線上語音路由中，指定這兩個 SBC。 如果一個 SBC 失敗，路由原則會將呼叫路由到第二個 SBC。


## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
