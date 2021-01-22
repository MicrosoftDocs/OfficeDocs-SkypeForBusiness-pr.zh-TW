---
title: 設定會話邊界控制器 - 多個租使用者
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何在 SBC (設定一個會話邊界控制器) 為 Microsoft 合作夥伴及/或 PSTN 電信) 服務多個租使用者。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 343e2d1aedefd34de452df8da6ce9a5ad1a726ba
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923845"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>設定多個租用戶的工作階段邊界控制器

直接路由支援在 SBC (上) 一個會話邊界控制器，以服務多個租使用者。

> [!NOTE]
> 此案例是專為 Microsoft 合作夥伴和/或 PSTN 電信平臺所設計，本文稍後稱為電信者。 電信業者銷售傳送至 Microsoft Teams 的電話語音服務給客戶。 

電信公司：
- 在資料中心部署和管理 SBC (客戶不需要執行 SBC，而且他們會在 Teams 用戶端用戶端服務中從電信業者) 。
- 將 SBC 與多個租使用者相互連接。
- 為客戶提供 PSTN 服務。
- 端對端管理通話品質。
- PSTN 服務另行收費。

Microsoft 並未管理電信電信公司。 Microsoft 提供 PBX (Microsoft Phone System) Teams 用戶端。 Microsoft 也會為可與 Microsoft Phone System 一同使用的手機和認證 SBC 提供認證。 選擇電信業者之前，請確定您的選擇具有通過認證的 SBC，而且可以端對端管理語音品質。

以下是設定案例的技術執行步驟。

**只提供電信商：**
1. 根據認證 SBC 廠商的指示部署 SBC，並針對託管案例 [進行設定](#deploy-and-configure-the-sbc)。
2. 在電信業者租使用者中註冊基本功能變數名稱，並要求萬用字元憑證。
3. 針對每個客戶註冊子域，這是基本網域的一部分。

**具有客戶全域系統管理員的電信公司：**
1. 將子功能變數名稱稱新增到客戶租使用者。
2. 啟動子功能變數名稱稱。
3. 設定從電信公司到客戶租使用者的主幹，並配置使用者。

*請務必瞭解 DNS 基本功能，以及 Microsoft 365 或 Office 365 中的功能變數名稱管理方式。在 [繼續進行之前，先查看取得 Microsoft 365 或 Office 365 網](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 域的協助。*

## <a name="deploy-and-configure-the-sbc"></a>部署及設定 SBC

如需如何部署及設定 SBC 託管案例 SBC 的詳細步驟，請參閱 SBC 廠商的檔。

- **AudioCodes：** [Direct Routing Configuration notes，](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)the SBC 主機託管案例的組式描述于「將 AudioCodes SBC 連結至 Microsoft Teams 直接路由主機管理模型組組記」。 
- **Oracle：Direct** [Routing Configuration notes，](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)the configuration of SBC hosting scenario is described in the "Microsoft" section. 
- **功能區通訊：** 請參閱功能區 [通訊 SBC 核心版 Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)設定指南，以瞭解如何設定功能區核心系列 SB0 及此頁面功能區最佳作法 - 設定 Microsoft Teams 直接路由 [SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)的電信業者
- **TE-Systems (anynode) ：**  請在 [TE-Systems Community](https://community.te-systems.de/) 頁面上註冊，以瞭解如何為多個租使用者設定 anynode SBC 的檔和範例。
- **元數：**  請在 [Metasw一社群頁面](https://manuals.metaswitch.com/MAN39555) 註冊，以瞭解如何為多個租使用者啟用 Perimeta SBC 的檔。

> [!NOTE]
> 請注意如何設定「連絡人」標頭。 連絡人標題可用來在傳入的邀請訊息上尋找客戶租使用者。 

## <a name="register-a-base-domain-and-subdomains"></a>註冊基本網域和子域

針對託管案例，您必須建立：
- 電信業者所擁有的一個基礎功能變數名稱。
- 這是每個客戶租使用者中基礎功能變數名稱的一部分之子域。

在下列範例中：
- Adatum 是一家電信業者，提供網際網路和電話語音給數位客戶。
- Woodgrove Bank、Contoso 和 Adventure Works 是三個擁有 Microsoft 365 或 Office 365 網域但從 Adatum 接收電話語音的客戶。

子域必須與要為客戶配置的主幹 FQDN 名稱與傳送邀請給 Microsoft 365 或 Office 365 時，連絡人標頭中的 FQDN 相符。 

當通話抵達 Microsoft 365 或 Office 365 直接路由介面時，該介面會使用連絡人標頭，尋找使用者應查看的租使用者。 直接路由不會在邀請上使用電話號碼查找，因為有些客戶的非 DID 號碼可能會與數個租使用者重迭。 因此，若要找出以電話號碼來尋找使用者的確切租使用者，在連絡人標頭中必須輸入 FQDN 名稱。

*如需在 Microsoft  [365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織中建立功能變數名稱的資訊，請參閱取得 Office 365 網域的協助。*

下圖摘要說明基礎網域、子域和連絡人標頭的需求。

![顯示網域和連絡人頁眉需求的圖表](media/direct-routing-1-sbc-requirements.png)

SBC 需要憑證來驗證連結。 針對 SBC 主機服務案例，電信業者需要向 CN 和/或 SAN .base_domain (要求憑證，例如 *\* \* .customers.adatum.biz) 。* 此憑證可用來驗證從單一 SBC 服務的多個租使用者之連結。


下表是一個組配置的範例。


|新的功能變數名稱 |類型|註冊  |SBC 憑證 CN/SAN  |範例中的租使用者預設網域  |傳送來電給使用者時，SBC 必須在連絡人標頭中顯示之 FQDN 名稱|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    基地     |     在電信公司租使用者中  |    \*.customers.adatum.biz  |   adatum.biz      |NA，這是服務租使用者，沒有使用者 |
|sbc1.customers.adatum.biz|    子域  |    在客戶租使用者中  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   子域 | 在客戶租使用者中   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   子域 | 在客戶租使用者中 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

若要設定基底和子域，請遵循下列所述步驟。 在範例中，我們會針對 Woodgrove Bank 租使用者 (customers.adatum.biz) 一個客戶帳戶設定基本功能變數名稱 (sbc1.customers.adatum.biz域) 。

> [!NOTE]
> 在sbcX.customers.adatum.biz租使用者中啟用語音功能。 sbcX 可以是任何唯一且有效的 Alphanumeric 主機名稱。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>在電信公司租使用者中註冊基本功能變數名稱

**這些動作是在電信公司租使用者中執行。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>確定您擁有電信公司租使用者的適當許可權

如果您是以全域系統管理員的名號，在 Microsoft 365 系統管理中心內，才能新增網域。 

若要驗證您擁有的角色，請前往 Microsoft 365 系統管理中心 (、前往使用者作用中使用者，然後確認您擁有 https://portal.office.com)   >  全域系統管理員角色。 

有關系統管理員角色以及如何在 Microsoft 365 或 Office 365 中指派角色詳細資訊，請參閱關於 [系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>新增基本網域至租使用者並進行驗證

1. 在 Microsoft 365 系統管理中心，請前往設定  >  **網域**  >  **新增網域**。
2. 在 **輸入您擁有之網域的** 方塊中，輸入基本網域的 FQDN。 在下列範例中，基本網域為 *customers.adatum.biz。*

    ![顯示新增網域頁面的螢幕擷取畫面](media/direct-routing-2-sbc-add-domain.png)

3. 按一下 [ **下一步**。
4. 在範例中，租使用者已經有adatum.biz驗證功能變數名稱。 精靈不會要求進行其他驗證，因為 customers.adatum.biz是已登錄名稱的子域。 不過，如果您新增之前尚未驗證的 FQDN，則需要執行驗證程式。 以下說明驗證 [程式](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。

    ![顯示已驗證功能變數名稱確認的螢幕擷取畫面](media/direct-routing-3-sbc-verify-domain.png)

5. 按 **[下** 一步，在 [ **更新 DNS** 設定> 頁面上，選取我要新增 **DNS** 記錄，然後按一下 [下一 **步**。
6. 在下一頁中，清除所有值 (除非您要使用 Exchange、SharePoint 或 Teams/商務用 Skype) 功能變數名稱，請按一下 [下一步，然後按一下 [完成。 請確定您的新網域是設定完成狀態。

    ![顯示設定完成狀態之網域的螢幕擷取畫面](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>啟用功能變數名稱

註冊功能變數名稱之後，您必須新增至少一個 E1、E3 或 E5 授權使用者，並指派 SIP 位址的 SIP 位址的 FQDN 部分，與所建立之基本網域配對，以啟用該功能變數名稱。 在網域啟用之後，授權 (最多可能需要 24 小時的時間) 。

> [!NOTE]
> 電信業者租使用者必須保留指派給租使用者至少一個 E1/E3/E5/M365 商務版授權，以避免移除商務用 Skype 組配置。 

*如需在 [Microsoft 365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織中新增使用者之詳細資訊，請參閱取得 Microsoft 365 或 Office 365 網域的協助。*

例如：test@customers.adatum.biz

![基礎網域啟用頁面的螢幕擷取畫面](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>在客戶租使用者中註冊子功能變數名稱稱

您必須為每個客戶建立唯一的子功能變數名稱稱。 在此範例中，我們會建立一個子域sbc1.customers.adatum.biz租使用者中的子域，其預設功能變數名稱是 woodgrovebank.us。

**下方所有動作都位在客戶租使用者中。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>確定您擁有客戶租使用者的適當許可權

如果您是以全域系統管理員的名名，在 Microsoft 365 系統管理中心內，才能新增網域。 

若要驗證您擁有的角色，請前往 Microsoft 365 系統管理中心 (、前往使用者作用中使用者，然後確認您擁有 https://portal.office.com)   >  全域系統管理員角色。 

有關系統管理員角色以及如何在 Microsoft 365 或 Office 365 中指派角色詳細資訊，請參閱關於 [系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>新增子域至客戶租使用者並驗證
1. 在 Microsoft 365 系統管理中心，請前往設定  >  **網域**  >  **新增網域**。
2. 在 **輸入您擁有網域的** 方塊中，輸入此租使用者子域的 FQDN。 在下面的範例中，子域是sbc1.customers.adatum.biz。

    ![新增網域頁面的螢幕擷取畫面](media/direct-routing-5-sbc-add-customer-domain.png)

3. 按一下 [ **下一步**。
4. FQDN 從未在租使用者中註冊過。 在下一個步驟中，您將必須驗證網域。 請 **改為選取新增 TXT 記錄**。 

    ![驗證網域頁面的螢幕擷取畫面](media/direct-routing-6-sbc-verify-customer-domain.png)

5. 按 **[下** 一步，然後記下為了驗證功能變數名稱而產生的 TXT 值。

    ![在驗證網域頁面上的文字記錄螢幕擷取畫面](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 使用電信公司 DNS 主機服務提供者中上一個步驟中的值來建立 TXT 記錄。

    ![顯示建立 TXT 記錄的螢幕擷取畫面](media/direct-routing-8-sbc-txt-record.png)

    詳情請參閱在任何 DNS 主機服務提供者建立 [DNS 記錄](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。

7. 返回客戶的 Microsoft 365 系統管理中心，然後按一下 [ **驗證**。 
8. 在下一頁中，選取 **[我將** 自己新增 DNS 記錄，然後按一下 [下一 **步**。

    ![更新 DNS 設定頁面上選項的螢幕擷取畫面](media/direct-routing-9-sbc-update-dns.png)

9. 在 [ **選擇您的線上服務** ; 頁面上，清除所有選項，然後按一下 [下 **一步**。

    ![選擇您的線上服務頁面的螢幕擷取畫面](media/direct-routing-10-sbc-choose-services.png)

10. 按一下 **[更新** DNS 設定 **頁面的完成** 時間。

    ![更新 DNS 設定頁面的螢幕擷取畫面](media/direct-routing-11-sbc-update-dns-finish.png)

11. 請確保已設定 **完成狀態**。 
    
    ![顯示安裝完成狀態的頁面螢幕擷取畫面](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> 個別用戶端的基本 URL 和子域必須位於相同的租使用者上，才能新增直接 _路由主幹_ 。

### <a name="activate-the-subdomain-name"></a>啟動子功能變數名稱稱

註冊功能變數名稱之後，您必須新增至少一個使用者，並指派 SIP 位址的 SIP 位址 FQDN 部分，且該位址符合客戶租使用者中已建立之子域，以啟用該功能變數名稱。 在子域啟用之後，使用者可能會撤銷授權 (最多可能需要 24 小時的時間) 。

*如需在 [Microsoft 365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織中新增使用者之詳細資訊，請參閱取得 Microsoft 365 或 Office 365 網域的協助。*

例如：test@sbc1.customers.adatum.biz

![子域頁面的啟用螢幕擷取畫面](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>建立主幹及提供使用者

在直接路由的初次發行中，Microsoft 要求每個使用 New-CSOnlinePSTNGateway 的客戶租使用者 () 新增一條主幹。

不過，有兩個原因未達最佳結果：
 
- **負荷管理**。 例如，將 SBC 卸去或耗盡，會變更某些參數，例如啟用或停用媒體旁路。 變更埠需要以執行 Set-CSOnlinePSTNGateway (，來變更多個租使用者中的參數) ，但實際上是同一個 SBC。 

-  **負荷處理**。 收集及監控主幹健康情況資料 - 從多個邏輯主幹收集的 SIP 選項，實際上，同一個 SBC 和相同的實體主幹，會降低路由資料的處理速度。
 
根據這項意見回饋，Microsoft 帶來新的邏輯來為客戶租使用者提供主幹。

已推出兩個新實體：
-    使用 New-CSOnlinePSTNGateway 命令在電信公司租使用者中註冊的電信公司主幹，例如 New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true。

-    不需要註冊的衍生主幹。 它只是從電信公司主幹中新增的所需的主機名稱。 它會從電信商主幹衍生其所有組設定參數。 衍生的主幹不需要在 PowerShell 中建立，而電信業者主幹的關聯是以 FQDN 名稱為基礎 (請參閱下方) 。

**提供邏輯和範例**

-    電信公司只需要使用 (命令，在電信) 線中設定及管理單一Set-CSOnlinePSTNGateway線。 在上例中，它adatum.biz;
-    在客戶租使用者中，電信公司只需要將衍生的主幹 FQDN 新增到使用者的語音路由策略。 不需要為主幹New-CSOnlinePSTNGateway線。
-    如名稱所示，衍生的主幹會繼承或衍生電信公司主幹的所有設定參數。 例子：
-    Customers.adatum.biz – 需要在電信公司租使用者中建立之電信公司主幹。
-    Sbc1.customers.adatum.biz – 客戶租使用者中的衍生主幹，不需要在 PowerShell 中建立。  只要在線上語音路由政策中，即可在客戶租使用者中新增衍生主幹名稱，而不必建立。
-   電信公司必須設定 DNS 記錄，以解析衍生的主幹 FQDN 到電信公司 SBC IP 位址。

-    在電信電信 (租使用者) 進行的任何變更，都會自動適用于衍生主幹。 例如，電信公司可以變更電信公司主幹上的 SIP 埠，這項變更適用于所有衍生的主幹。 設定主幹的新邏輯簡化了管理，因為不需要前往每個租使用者，也不需要變更每一條主幹上的參數。
-    選項只會送到電信公司主幹 FQDN。 電信公司主幹的健康情況狀態會適用于所有衍生主幹，並用於路由決策。 進一瞭解更多直接 [路由選項](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)。
-    電信公司可以消耗電信公司主幹的消耗，而所有衍生的主幹也會耗盡。 
 

**從先前的模型移往電信運輸主幹**
 
針對從電信公司託管模型的目前執行移向新模型，電信公司需要重新建立客戶租使用者主幹。 使用線路離開電信Remove-CSOnlinePSTNGateway (租使用者中的主幹，移除客戶租使用者中的) -

我們強烈建議您儘快移移至新的解決方案，我們將加強使用電信號和衍生主幹模型的監控與部署功能。
 

請參閱 [SBC](#deploy-and-configure-the-sbc) 廠商有關在連絡人標頭中傳送子域之 FQDN 名稱的指示。

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>設定靜音租使用者容錯移轉的考慮事項 

若要為多租使用者環境設定容錯移轉，您必須執行下列操作：

- 針對每個租使用者，為兩個不同的 SBC 新增 FQDN。  例如：

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- 在使用者的線上語音路由策略中，指定兩個 SBC。  如果某個 SBC 失敗，路由策略會路由呼叫到第二個 SBC。


## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
