---
title: 在 Microsoft 團隊中管理您的商務用應用程式
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何將自訂團隊 app 從開發開發到部署。
ms.openlocfilehash: cd64ff0a3307ada0f1fbfaf29b94cfcd1da3c0df
ms.sourcegitcommit: d6a0ff7f00defda2b58726f5f0f0fac871f46ab7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2019
ms.locfileid: "37682693"
---
# <a name="manage-your-line-of-business-apps-in-microsoft-teams"></a>在 Microsoft 團隊中管理您的商務用應用程式

本文提供如何將您的小組 app 從開發開發到部署的端對端指導方針。 本指南主要說明 app 的小組各部分，且適用于 IT 專業人員。 如需開發小組 app 的詳細資訊，請參閱[這裡](https://docs.microsoft.com/microsoftteams/platform)。

![從開發到部署的應用程式概覽](media/manage-your-lob-apps.png)

## <a name="getting-started"></a>快速入門

若要在小組中建立及管理企業往來（LOB）應用程式，您需要兩個租使用者：用於開發和生產租使用者的測試租使用者。

> [!NOTE]
> 如果您還沒有測試租使用者，您可以使用 Office 365 開發人員程式，快速建立一個並填入測試資料。 [深入瞭解](https://developer.microsoft.com/office/dev-program)。

## <a name="step-1-develop-and-test"></a>步驟1：開發與測試

### <a name="create-test-users"></a>建立測試使用者

請確定您的開發人員（無論是內部還是外部）在您的測試租使用者中有帳戶。 [深入瞭解如何新增使用者](https://docs.microsoft.com/office365/admin/add-users/add-users)。

### <a name="allow-custom-apps-in-the-test-tenant"></a>允許測試租使用者中的自訂應用程式

若要為開發人員提供測試所需的存取權，請允許測試租使用者中的所有使用者上傳自訂應用程式（也稱為邊載）。 這可讓開發人員上傳自訂的應用程式，以供個人或跨測試租使用者使用，而不需將 app 提交到 [小組 app] 存放區。 上傳自訂的應用程式可讓開發人員在您更廣泛地發佈 app 之前先測試應用程式。

若要允許使用者上傳自訂應用程式，請依照下列步驟執行：

1. 開啟 [**允許與自訂應用程式互動**] 的全組織性設定。 若要執行此動作：
    1. 在[Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，移至 [**團隊 app** > **許可權原則**]，然後按一下 [**全組織性設定**]。
    2. 開啟 [**自訂應用程式**] 底下的 [**允許與自訂應用程式互動**]，然後按一下 [**儲存**]。

    ![[允許與自訂應用程式互動] 的螢幕擷取畫面-全組織性設定](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. 開啟全域 app 設定原則中的 [上**傳自訂應用程式**] 設定。 若要執行此動作：
    1. 在[Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，移至 [**團隊 app** > **設定原則**]，然後按一下 [**全域（組織範圍預設值）** ] 原則。
    2. 開啟 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。

    ![[上傳自訂應用程式] app 設定策略設定的螢幕擷取畫面](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> 此外，小組層級也會有上傳自訂應用程式設定。 根據預設，此設定為 [開啟]。 不過，如果開發人員無法將自訂應用程式上傳至團隊，請按照[這裡](teams-custom-app-policies-and-settings.md#configure-the-team-custom-app-setting)的步驟來檢查該設定。

### <a name="create-your-app"></a>建立您的應用程式

開發人員現在應該擁有建立您 app 所需的專案。 請參閱[這裡](https://docs.microsoft.commicrosoftteams/platform)以取得相關指導方針。

## <a name="step-2-validate-in-production"></a>步驟2：在生產中驗證

### <a name="get-the-app-package"></a>取得應用程式套件

當應用程式準備好在生產中使用時，開發人員應該會產生應用程式套件。 他們可以使用[應用程式 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)來執行此程式。 他們會以 .zip 格式傳送檔案。

Microsoft 使用[這些指導方針](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval)，以確保 app 符合全域團隊 app store 的品質與安全性標準。

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a>允許信任的使用者上傳生產租使用者中的自訂應用程式

若要驗證 app 在您的生產租使用者中是否正常運作，您必須允許您的組織中的人員和/或受信任的使用者上傳自訂應用程式。  與 [測試租使用者] 步驟中的 [舊版[允許自訂應用](#allow-custom-apps-in-the-test-tenant)程式] 相似，您可以使用 app 設定原則來執行這項作業。

> [!NOTE]
> 如果您不滿意將 app 上傳到您的生產租使用者進行驗證，即使您是自己或受信任的使用者，您也可以略過此步驟，然後遵循步驟3和4，將 unvalidated 應用程式上傳到您的租使用者應用程式存放區。 然後，將該 app 的存取許可權制為只有您自己和您信任的使用者。 然後，這些使用者就可以從租使用者應用程式商店取得 app 來執行驗證。 驗證應用程式後，請使用相同的許可權原則來開啟 access，並將 app 滾出以供生產使用。

若要允許信任的使用者上傳自訂應用程式，請依照下列步驟執行：

1. 開啟 [**允許與自訂應用程式互動**] 的全組織性設定。 若要執行此動作：
    1. 在[Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，移至 [**團隊 app** > **許可權原則**]，然後按一下 [**全組織性設定**]。
    2. 開啟 [**自訂應用程式**] 底下的 [**允許與自訂應用程式互動**]，然後按一下 [**儲存**]。
2. 關閉全域 app 設定原則中的 [**上傳自訂應用程式**] 設定。 若要執行此動作：
    1. 在[Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，移至 [**團隊 app** > **設定原則**]，然後按一下 [**全域（組織範圍預設值）** ] 原則。
    2. 關閉 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。
3. 建立新的應用程式設定原則，以允許上傳自訂應用程式，並將它指派給您的一組受信任的使用者。 若要執行此動作：
    1. 在[Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，移至 [**團隊 app** > **設定原則**]，然後按一下 [**新增**]。 提供新原則的名稱和描述、開啟 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。
    2. 選取您建立的新原則，然後按一下 [**管理使用者**]。 搜尋使用者 **，按一下 [****新增**]，然後按一下 [套用]。 重複此步驟，將原則指派給所有信任的使用者。

        ![[新增應用程式設定原則] 頁面的螢幕擷取畫面](media/manage-your-lob-apps-new-app-setup-policy.png)

    這些使用者現在可以上傳應用程式資訊清單，以驗證 app 在生產租使用者中是否正常運作。

## <a name="step-3-upload-to-the-tenant-apps-catalog"></a>步驟3：上傳至租使用者應用程式目錄

若要讓 [租使用者應用程式] 存放區中的使用者使用 app，請上傳 app。 您可以使用小組桌面用戶端來執行此動作。 請按照[這裡](tenant-apps-catalog-teams.md#go-to-the-tenant-apps-catalog)的步驟進行。

![[應用程式] 頁面的螢幕擷取畫面](media/manage-your-lob-apps-store.png)

## <a name="step-4-configure-and-assign-permissions"></a>步驟4：設定及指派許可權

### <a name="control-access-to-the-app"></a>控制對應用程式的存取權

根據預設，所有使用者都可以在 [團隊 app] 商店中存取此應用程式。 若要限制及控制誰有權使用該應用程式，您可以建立並指派新的應用程式許可權原則。 請按照[這裡](teams-app-permission-policies.md#create-a-custom-app-permission-policy)的步驟進行。

![[新增應用程式許可權原則] 頁面的螢幕擷取畫面](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a>釘選應用程式供使用者探索

根據預設，使用者必須移至 [小組 app] 商店，然後流覽或搜尋。 若要讓使用者能夠輕鬆存取應用程式，您可以將應用程式釘選到 [團隊] 中的應用程式行。 若要這樣做，請建立新的應用程式設定原則，並將它指派給使用者。 請按照[這裡](teams-app-setup-policies.md#create-a-custom-app-setup-policy)的步驟進行。

![[新增釘選的 app] 窗格的螢幕擷取畫面](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a>步驟5：更新應用程式

![從開發到部署的應用程式概覽](media/manage-your-lob-apps-update.png)

若要更新應用程式，開發人員應該繼續遵循[步驟 1](#step-1-develop-and-test)和[步驟 2](#step-2-validate-in-production)。

您可以透過租使用者應用程式目錄來更新應用程式。 若要這樣做，請在團隊桌面用戶端，移至**針對&lt;您的租&gt;使用者名稱所建的** **app** > ，按一下 **...** 按一下應用程式右上角的，然後按一下 [**更新**]。 這麼做會取代租使用者應用程式目錄中的現有應用程式，而且擁有權限原則和設定原則都會針對更新的 app 保持強制執行。 

![在 [應用程式] 頁面上更新應用程式的螢幕擷取畫面](media/manage-your-lob-apps-update-app.png)