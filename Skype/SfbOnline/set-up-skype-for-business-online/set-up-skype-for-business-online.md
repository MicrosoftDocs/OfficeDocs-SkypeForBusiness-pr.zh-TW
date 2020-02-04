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
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.custom:
- Setup
- Alchemy
- LIL_Placement
description: '瞭解如何為您的組織設定您的網域、使用者、IM 和目前狀態，以安裝商務用 Skype。 另請參閱如何設定音訊會議、電話系統和通話方案，以及 Skype 會議廣播。 '
ms.openlocfilehash: d30a141b80ade00ef03bafdfab388df56e4b1b7d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692868"
---
# <a name="set-up-skype-for-business-online"></a>設定商務用 Skype Online

您必須具備 Office 365 全域系統管理員許可權，才能設定商務用 Skype。 如果您的防火牆或 proxy 伺服器限制存取網路元件，請考慮聘用[Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)來為您設定商務用 Skype。

## <a name="setting-up-skype"></a>設定 Skype

看起來您需要協助設定 Office 365 訂閱的 Skype。 您可以依照本文所述的步驟，讓您的設定完成。

## <a name="1-plan-for-skype-for-business"></a>1. 規劃商務用 Skype

如果您有**[Office 365 商務版 Premium](https://products.office.com/en-us/business/office-365-business-premium)** 或**商業基本**版，您可以使用商務用 Skype，在您的訂閱中的其他人對您的公司進行線上通話。 例如，如果您的公司有10人，您就可以[開始使用商務用 skype 進行 IM 和線上會議](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd)，以及在執行下列步驟2-6 後使用商務用 skype 進行商務用 Skype 的[會議](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851)。 您也可以[在 Outlook 中設定商務用 Skype 會議，在](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA)線上開會！

如果您想要使用商務用 Skype 撥打與接聽公司*外部*人員的**通話**：

- **選項1。使用免費的[Skype app](https://www.skype.com/)**。 如果您的公司非常小（例如，1-2 人），使用 Skype app 就是更好的做法。 在國內和國際通話中使用的成本較低。 您仍可召開會議通話、進行視頻通話，以及分享簡報的桌面。 [查看工資率與付款選項](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)。

- **選項2。升級您的方案，並購買電話系統和 Office 365 通話方案**。 您最簡單的方法就是了解這項成本的多少，然後再進行這個切換，就能[與商務產品支援人員-系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)並讓他們為您執行所有工作。

若要深入瞭解，請參閱[規劃商務用 Office 365 的設定](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)。

## <a name="2-sign-in-to-office-365"></a>2. 登入 Office 365
<a name="bkmk_signin"> </a>

商務用 Skype Online 是 Office 365 套件服務套件的一部分。 若要設定商務用 Skype Online，您必須登入 Office 365。 具體做法如下：

1. 找出您的 Office 365 使用者識別碼（例如， <em>rob@fourthcoffee.com</em> ）。 您收到來自 Microsoft Online 服務小組的電子郵件，其中包含您購買商務用 Skype Online 時所建立的 Office 365 使用者識別碼。 [郵件] 看起來像這樣：

    ![在您註冊商務用 Skype Online 之後收到的歡迎電子郵件範例。 它包含您的 Office 365 使用者識別碼。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. 登入系統[管理中心](https://admin.microsoft.com)，並輸入您的 Office 365 使用者識別碼和密碼。 

## <a name="3-set-up-your-domain-and-users"></a>3. 設定您的網域和使用者
<a name="bkmk_users"> </a>

現在您已登入 Office 365，您可以在組織中設定您的網域和人員，以使用商務用 Skype Online。

1. [新增網域和使用者至 office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611)：使用 office 365 設定向導，將您的自訂網域（例如*fourthcoffee.com*）設定為 office 365。 **根據預設，Office 365 安裝精靈包括設定商務用 Skype Online，以及建立您的商務用 Skype 使用者識別碼。** 如果您已使用此嚮導來設定您的 Office 365 網域，就表示您已完成這個步驟。

2. [檢查您的網域和 dns](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0)連線：使用我們的工具-網域疑難排解程式-確認您的網域和 dns 設定正確無誤。 如此一來，我們將會在稍後協助您進一步找出任何設定問題，因為您可以將 DNS 設定排除為未來問題的來源。

3. [Office 365 url 與 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)：大多數小型企業不需要執行此步驟。 **但如果您擁有的防火牆或 proxy 伺服器限制存取網路元件**，您必須建立規則，以允許存取商務用 Skype Online 端點。 這個高級步驟最適合透過設定防火牆和 proxy 伺服器的人來執行。 如果您之前還沒有這麼做，請考慮聘用[Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)來為您設定商務用 Skype。

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. 在您的組織中設定 IM 和目前狀態
<a name="bkmk_IM"> </a>

立即訊息（IM）與目前狀態（[控制商務用 skype 中您目前狀態資訊的存取](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)）是商務用 skype 隨附的基本功能。 根據預設，貴公司中的人員可以彼此進行 Skype 和 IM。

1. **選擇您的商務用 Skype 使用者可以與其他人通訊：**

   - [允許使用者與外部商務用 Skype 使用者聯繫](allow-users-to-contact-external-skype-for-business-users.md)您*和*其他企業都需要設定您的系統。

     **重要**：如果您的企業中有兩個網域（例如 rob@contosowest.com 和 ina@contosoeast.com），您需要執行此步驟，讓所有使用者都能彼此通訊。

   - [讓商務用 Skype 使用者新增](let-skype-for-business-users-add-skype-contacts.md)您企業外部的 skype 連絡人

2. **選擇誰可以查看同事是否處於線上狀態：**[目前狀態] 功能會顯示誰在線上，以及其可用性，例如 [可用]、[忙碌]、[離開] 或 [簡報中]。

    ![使用個人訊息的人員線上狀態範例。](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    您可以為企業中的每個人選擇預設設定：

   - 自動將人員的線上狀態顯示給組織中的所有人

   - 僅將人員的線上狀態顯示給其連絡人

如需相關指示，請參閱[在商務用 Skype Online 中設定目前狀態](configure-presence-in-skype-for-business-online.md)。

## <a name="5-download-and-install-skype-for-business"></a>5. 下載並安裝商務用 Skype
<a name="bkmk_download"> </a>

若要在您的 PC、Mac 或行動裝置上使用商務用 Skype，您和企業中的其他人必須先在您的裝置上安裝商務用 Skype 下載。

- [安裝商務用 Skype](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)：說明如何從 Office 365 入口網站下載應用程式，並將它安裝在您的 PC 或 Mac 上。

- [在 Office 365 中部署商務用 Skype 用戶端](deploy-the-skype-for-business-client-in-office-365.md)：在大型企業中部署應用程式的指示。

- [安裝商務用 skype](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)：在 Android 裝置、iOS 裝置和 Windows 手機上下載、安裝及登入商務用 skype。

- [開啟或關閉行動電話通知](turn-on-or-off-mobile-phone-notifications.md)：當您在行動裝置上安裝商務用 Skype 時，您和企業中的其他人會收到有關傳入和未接的立即訊息的通知。

## <a name="6-test-to-make-sure-everything-is-working"></a>6. 測試以確定一切正常運作
<a name="bkmk_test"> </a>

首先，測試您與貴組織中的其他人是否可以進行[影片：登入和登出商務用 Skype](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)。 檢查您是否可以相互傳送即時消息、查看彼此的目前狀態，以及嘗試快速會議。

常見問題? 請執行下列步驟：

- [需要登入商務用 Skype 的協助嗎？](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05)常見的登入問題。

- [客戶支援部門-系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。 我們在這裡協助您！

## <a name="do-you-want-to-set-up-other-available-features"></a>您想要設定其他可用的功能嗎？
<a name="bkmk_more"> </a>

在設定更多功能前，請確定您有授權給他們。 [商務用 Skype 和 Microsoft 團隊附加元件授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a>設定音訊會議

有時候貴組織中的人員必須使用電話撥入會議。 商務用 Skype 包括音訊會議功能，只適用于這種情況！ 使用者可以使用電話撥入商務用 Skype 會議，而不是在行動裝置或電腦上使用商務用 Skype 應用程式。

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>在 Office 365 中設定電話系統和通話方案

Office 365 中的 [電話系統] 功能可為您的企業提供電話系統。 您組織中其他商務用 Skype 人員的通話是免費的，而且您的員工可以接收來自對方和外部呼叫者的語音信箱。 以下是您使用電話系統所取得的結果。

當您新增通話方案服務時，員工會在商務用 Skype 中取得主要電話號碼。 他們可以撥打和接聽公司外部的電話。 在 VoIP 手機、電腦和行動裝置上，他們可以撥打語音通話。 而且，在緊急情況下，他們可以呼叫911取得協助。

如需逐步設定指示，請參閱設定通話方案。

### <a name="set-up-skype-meeting-broadcast"></a>設定 Skype 會議廣播

Skype 會議廣播是一項功能，可讓您使用最多10000的出席者來製作、主持及廣播會議。 **若要深入瞭解它的運作方式，請參閱[什麼是 Skype 會議廣播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**

以下是設定 Skype 會議廣播的步驟概覽：

1. [指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)：指派**商務用 Skype Online**或**企業方案**授權給即將**主持**廣播會議的每一個人。

2. [啟用 Skype 會議廣播](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md)：預設不會啟用此功能。 開啟之後，您的使用者就能與貴組織中的其他人主持廣播會議。

3. [為您的 Skype 會議廣播設定您的網路](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)：如果您想要將網路研討會及其他廣播託管給組織外部的出席者，您必須設定您的網路。

4. 排程[Skype 會議廣播](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553)，並[加入 skype 會議廣播](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)：請確認 [廣播會議] 是透過排程 skype 會議廣播*https://portal.broadcast.skype.com* ，然後讓某人嘗試加入會議來運作。

## <a name="learn-about-network-connectivity-requirements"></a>瞭解網路連線需求
<a name="bkmk_more"> </a>

在商務用 Skype 中，音訊、影片和應用程式共用品質會受到端對端網路連線品質的影響。 為了獲得最佳體驗，請務必確保您的公司網路與商務用 Skype Online 之間有高品質的連線。 如需網路和調諧資訊，請參閱[調整商務用 Skype Online 的效能](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)。

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>所有設定完成了嗎？ 開始使用商務用 Skype
<a name="bkmk_more"> </a>

[商務用 Skype 訓練](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba)：請參閱此訓練主題清單，協助您快速入門！

[啟動商務用 Skype 會議通話](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[在商務用 Skype 中設定視頻裝置選項](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[使用商務用 Skype 撥打和接聽視頻通話](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>相關主題
<a name="bkmk_more"> </a>

[規劃商務用 Skype Server 與商務用 Skype Online 之間的混合式連接](https://go.microsoft.com/fwlink/p/?linkid=400791)



