---
title: 設定商務用 Skype Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- Alchemy
- LIL_Placement
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
description: '瞭解如何設定網域、使用者、IM 和目前狀態，讓貴組織安裝商務用 Skype。 另請參閱如何設定音訊會議、電話系統與通話方案，以及 Skype 會議廣播。 '
ms.openlocfilehash: 0c357c1dbe5b91c06b385562bf31d5f1307bd240
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109959"
---
# <a name="set-up-skype-for-business-online"></a>設定商務用 Skype Online

您必須擁有全域系統管理員許可權，才能設定商務用 Skype。 如果您有防火牆或 Proxy 伺服器限制對網頁部分的存取權限，請考慮雇用 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 合作夥伴來設定商務用 Skype。

## <a name="setting-up-skype"></a>設定 Skype

您似乎需要協助設定 Microsoft 365 或 Office 365 訂閱的 Skype。 您可以按照本文中的步驟完成設定。

## <a name="1-plan-for-skype-for-business"></a>1. 商務用 Skype 方案

如果您有 **[Microsoft 365 商務](https://products.office.com/business/office-365-business-premium)** 進級版標準版或商務基本版，您可以使用商務用 Skype 撥打線上電話給您訂閱中的公司其他人員。 例如，如果您的公司有 10 人，在執行下列步驟 2-6 之後，您就能開始使用商務用 Skype 進行 [IM](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) 和線上會議，以及使用商務用 [Skype](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) 的會議。 您也可以在 [Outlook 中設定商務用 Skype 會議](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) 至線上會議！

如果您想要使用商務用 Skype 撥打和接聽來自公司外部 *人員* 的電話：

- **選項 1.使用免費的 [Skype 應用程式](https://www.skype.com/)**。 如果您擁有非常小型企業 (例如 1-2) ，使用 Skype 應用程式是更好的方法。 國內及國際通話費用較低。 您仍然可以進行電話會議、進行視音訊通話，以及共用桌面進行簡報。 [查看費率和付款選項](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)。

- **選項 2.升級您的方案，並購買 Office 365** 的電話系統與通話方案。 若要瞭解這項成本，然後進行切換，最簡單的方法就是與商務產品 [支援人員聯繫 -](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 系統管理說明，讓他們幫您完成所有工作。

若要深入瞭解，請參閱 [規劃商務用 Office 365 的設定](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)。

## <a name="2-sign-in-to-office-365"></a>2. 登錄 Office 365
<a name="bkmk_signin"> </a>

商務用 Skype Online 是 Office 365 服務套件的一部分。 若要設定商務用 Skype Online，您必須登錄 Office 365。 以下是您執行此工作的原因：

1. 尋找您的 Microsoft 365 或 Office 365 使用者識別碼 (例如<em>，rob@fourthcoffee.com) 。</em> 您收到來自 Microsoft Online Services 小組的電子郵件，其中包含您購買商務用 Skype Online 時所建立之 Microsoft 365 或 Office 365 使用者識別碼。 郵件看起來像這樣：

    ![註冊商務用 Skype Online 後收到的歡迎電子郵件範例。 它包含您的 Microsoft 365 或 Office 365 使用者識別碼。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. 請登錄系統 [管理中心，](https://admin.microsoft.com) 然後輸入您的 Microsoft 365 或 Office 365 使用者識別碼和密碼。 

## <a name="3-set-up-your-domain-and-users"></a>3. 設定您的網域和使用者
<a name="bkmk_users"> </a>

現在，您已登錄 Office 365，您可以將網域和貴組織的人員設定為使用商務用 Skype Online。

1. 新增網域和使用者至 [Office 365：使用 Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611)設定精靈來設定您的自訂網域 (例如 Office 365 *fourthcoffee.com)* 網域。 **根據預設，Office 365 設定精靈包括設定商務用 Skype Online 和建立商務用 Skype 使用者 ID。** 如果您已經使用精靈來設定 Office 365 的網域，則已完成此步驟。

2. [檢查您的網域和 DNS 連接](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0)：使用我們的工具 -網域疑難排解員 -檢查您的網域和 DNS 設定是否正確。 現在這麼做有助於日後找出任何設定問題，因為您可以排除 DNS 設定做為未來問題的來源。

3. [Office 365 URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)和 IP 位址範圍：大多數小型企業不需要執行此步驟。 **但是，如果您有防火牆或** Proxy 伺服器限制對網頁部分的存取權限，您必須建立規則，允許存取商務用 Skype Online 端點。 這是一個進一步步驟，最好由具有防火牆和 Proxy 伺服器組組經驗的人執行。 如果您之前尚未這麼做，請考慮雇用 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089) 來設定商務用 Skype。

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. 在貴組織中設定 IM 和目前狀態
<a name="bkmk_IM"> </a>

立即訊息 (IM) 目前狀態 ([控制在商務](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c) 用 Skype 中目前狀態資訊的存取權) 商務用 Skype 中的基本功能。 根據預設，您公司中的人員可以彼此使用 Skype 和 IM。

1. **選擇商務用 Skype 使用者可以與誰通訊：**

   - [允許使用者與外部商務用 Skype 使用者聯繫](allow-users-to-contact-external-skype-for-business-users.md) 您 *和其他*  企業都需要設定您的系統。

     **重要**：如果您的企業有兩個網域，例如 rob@contosowest.com 和 ina@contosoeast.com，您必須執行此步驟，讓所有使用者能夠彼此通訊。

   - [讓商務用 Skype 使用者新增商務用 Skype](let-skype-for-business-users-add-skype-contacts.md) 連絡人

2. **選擇誰查看同事是否線上：** 目前狀態功能會顯示誰在線上，以及他們的可用狀態，例如可用、忙碌、離開或展示。

    ![包含個人訊息之人員線上狀態範例。](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    您可以為公司中的每個人選擇預設設定：

   - 自動顯示人員的線上目前狀態給組織中的每個人

   - 只向連絡人顯示某人的線上目前狀態

有關指示，請參閱 [設定商務用 Skype Online 中的目前狀態](configure-presence-in-skype-for-business-online.md)。

## <a name="5-download-and-install-skype-for-business"></a>5. 下載並安裝商務用 Skype
<a name="bkmk_download"> </a>

若要在 PC、Mac 或行動裝置上使用商務用 Skype，您和公司中的其他人必須先在您的裝置上安裝商務用 Skype 下載。

- [安裝商務用 Skype：](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)說明如何從 Microsoft 365 系統管理中心下載應用程式，並安裝在您的電腦或 Mac 上。

- [在 Office 365](deploy-the-skype-for-business-client-in-office-365.md)中部署商務用 Skype 用戶端：在大型企業中部署應用程式的指示。

- [安裝商務用 Skype：](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)在 Android 裝置、iOS 裝置和 Windows 手機上下載、安裝及登錄商務用 Skype。

- [開啟或關閉行動電話](turn-on-or-off-mobile-phone-notifications.md)通知：當您在行動裝置上安裝商務用 Skype 時，您和公司中的其他人可以收到有關傳入和未接立即訊息的提醒。

## <a name="6-test-to-make-sure-everything-is-working"></a>6. 測試以確保一切正常
<a name="bkmk_test"> </a>

首先，測試您和公司中的其他人是否可以[視訊：登出和登出商務用 Skype。](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451) 檢查您是否可以彼此 IM、查看彼此的目前狀態，並嘗試快速會議。

問題？ 請執行下列動作：

- [需要協助來登錄商務用 Skype 嗎？](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) 常見的登錄問題。

- [請連絡商務產品的客戶支援 - 管理說明](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。 我們在此提供協助！

## <a name="do-you-want-to-set-up-other-available-features"></a>您想要設定其他可用的功能嗎？
<a name="bkmk_more"> </a>

設定更多功能之前，請確定您擁有這些功能的授權。 [商務用 Skype 和 Microsoft Teams 附加元件授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a>設定音訊會議

有時候，貴組織的人需要使用電話來加入會議。 商務用 Skype 包含音訊會議功能，適用于此情況！ 使用者可以使用電話撥打商務用 Skype 會議，而不是在行動裝置或 PC 上使用商務用 Skype 應用程式。

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>在 Office 365 中設定電話系統和通話方案

Office 365 中的電話系統功能提供您商務用的電話系統。 您可以免費撥打給貴組織中其他商務用 Skype 人員，而且您的員工可以接收彼此和外部來電者的語音信箱。 以下是使用電話系統取得功能。

當您新增通話方案服務時，您的員工會取得商務用 Skype 的主要電話號碼。 他們可以撥打和接聽公司外的電話。 他們可以在 VoIP 電話、電腦和行動裝置上撥打語音通話。 萬一發生緊急事件，他們可以撥打 911 以尋找協助。

有關逐步設定指示，請參閱設定通話方案。

### <a name="set-up-skype-meeting-broadcast"></a>設定 Skype 會議廣播

Skype 會議廣播功能可讓您製作、主持及廣播多達 10，000 位出席者的會議。 **若要深入瞭解其運作方式，請參閱什麼是 [Skype 會議廣播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**

以下是設定 Skype 會議廣播的步驟概觀：

1. [指派或移除商務用 Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)授權：將商務用 **Skype Online** 或企業版方案授權指派給要主持廣播會議 **的每一個人**。

2. [啟用 Skype 會議廣播](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md)：根據預設，此功能不會啟用。 開啟之後，您的使用者將能夠主持與貴組織中其他人的廣播會議。

3. [設定 Skype](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)會議廣播的網路：如果您想要與組織外部的出席者主持網路研討會和其他廣播，您需要設定您的網路。

4. [排程 Skype 會議廣播](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) ，並擁有 [加入 Skype](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)會議廣播：確定廣播會議可以排程 Skype 會議廣播，然後讓某人嘗試  *https://portal.broadcast.skype.com*  加入會議。

## <a name="learn-about-network-connectivity-requirements"></a>瞭解網路連接需求
<a name="bkmk_more"> </a>

商務用 Skype 的音訊、視像和應用程式共用品質受到端對端網路連接品質的嚴重影響。 為了獲得最佳體驗，請務必確定公司網路與商務用 Skype Online 之間有高品質的連線。 有關網路和調整資訊，請參閱 [調整商務用 Skype Online 的績效](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)。

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>全部設定完成嗎？ 開始使用商務用 Skype
<a name="bkmk_more"> </a>

[商務用 Skype 訓練](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba)：查看這份訓練主題清單，説明您快速上手！

[啟動商務用 Skype 電話會議](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[在商務用 Skype 中設定視像裝置選項](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[使用商務用 Skype 撥打和接收視音訊通話](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>相關主題
<a name="bkmk_more"> </a>

[規劃商務用 Skype Server 與商務用 Skype Online 之間的混合式連線](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)