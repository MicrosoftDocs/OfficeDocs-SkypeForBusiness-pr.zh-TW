---
title: Microsoft Teams面板
ms.author: serdars
author: ManikaDhiman
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: 本文提供面板概觀及Microsoft Teams功能。
ms.openlocfilehash: 6970aaf1df6a318cd529840c9ea01d1de7cc24bfa81a6654d516ea3fc19afe9c
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2021
ms.locfileid: "57849778"
---
# <a name="microsoft-teams-panels"></a>Microsoft Teams面板

Microsoft Teams面板是安裝在會議空間外部的精簡觸控螢幕裝置，通常位於入口旁邊。 Teams面板，您可以一目了然地查看位置和會議詳細資料，並保留當場可用的會議空間。 您可以使用豐富的大型文字和色彩編碼標記，從遠處查看會議空間的可用性。

Teams是專用的Microsoft Teams裝置，可顯示透過 Teams 或 Outlook 365 日曆應用程式排定的會議詳細資料。 當會議詳細資料醒目顯示時，出席者可以確認他們位於正確的會議空間、正確的時間，以及適合的會議。

本文提供面板Teams概觀，並可協助規劃、傳遞及管理Teams裝置。

## <a name="features-supported-by-teams-panels"></a>由 Teams 支援的功能

Teams面板支援下列功能：

- **會議空間和會議詳細資料專用的顯示。** 您可以快速取得會議空間的詳細資訊，包括會議空間的位置和可用性。 對於保留的會議空間，您可以查看重要的會議詳細資料，例如會議標題、會議排程和會議召集人。
- **為臨時會議保留可用的會議空間。** 您可以使用觸控螢幕面板，在當場為臨時會議保留可用的會議空間，然後從Teams裝置或裝置Microsoft Teams 會議室Surface Hub會議。 
- **空間可用性狀態的色彩編碼標記。** 您可以使用生動的 LED 和主畫面指示器，近距離查看會議空間的可用性。 綠色表示會議空間可供使用，如有需要，您可以從面板本身保留會議空間。 紅色或紫色表示已保留會議空間。
- **自訂牆紙和保留狀態指示器。** 管理員可以透過設定變更面板的預設面板。 例如，系統管理員可以變更背景牆紙，或變更忙碌狀態指示器的色彩。
- **協助工具。** Teams面板有幾個協助工具功能，例如高對比文字，讓任何人都能更輕鬆地使用這些功能。

若要深入瞭解這些功能及如何使用這些功能，請參閱使用Microsoft Teams[面板](use-teams-panels.md)。

## <a name="partners-certified-for-teams-panels"></a>合作夥伴已Teams面板

您可以從下列其中Teams取得您的面板裝置：

- Cresron
- Yealink

## <a name="teams-panels-requirements"></a>Teams面板需求

部署面板裝置的硬體、軟體和網路需求可能會根據您部署的面板裝置類型而不同。 請參閱原始設備製造商 (OEM) 檔，瞭解一組裝置所需的功能。

## <a name="license-requirement"></a>授權需求

若要使用Teams面板，您需要[Microsoft Teams 會議室授權](../rooms/rooms-licensing.md)。

> [!Note]
> 如果您已經將Microsoft Teams 會議室部署在要安裝 Teams 面板的會議空間中，則不需要額外的授權Teams面板。

## <a name="deploy-teams-panels-devices"></a>部署Teams面板裝置

如果您參與規劃、部署及管理Teams面板裝置，則本節適用于您。 此區段並不適合這些面板的Teams使用者。

部署Teams面板裝置可以細分為下列工作：

- [會議空間庫存與功能規劃](#inventory-sites-and-meeting-spaces)：建立貴組織網站與會議空間的庫存，以部署Teams裝置。
- [採購](#procurement)：從所選裝置合作夥伴購買裝置。  
- [網站就緒](#site-readiness)：確認您的會議 (位置) 部署需求。
- [組配置與部署](#configuration-and-deployment)：建立資源帳戶，並將其指派給裝置。

## <a name="inventory-sites-and-meeting-spaces"></a>庫存網站和會議空間

盤點組織中現有的可預約會議空間。 識別在面板中部署範圍的網站Teams空間。 請與您的裝置和音訊-視覺小組合作，決定在何處以及如何安裝Teams面板裝置，以及安裝面板是否還需要任何其他硬體。

## <a name="procurement"></a>採購

根據部署面板Teams的會議空間數目，請從其中一個經過認證的合作夥伴取得Teams[裝置](#partners-certified-for-teams-panels)。 請流覽合作夥伴的網站，深入瞭解裝置和採購選項。

貴組織的會議空間在安裝或安裝裝置時，可能有不同的硬體需求。 例如，將裝置安裝在玻璃、灰布、幹牆或木材面板上所需的硬體可能不同。 請參閱裝置合作夥伴的檔，以尋找可用的安裝選項。

## <a name="site-readiness"></a>網站準備就緒

當訂購的裝置傳送給貴組織時，請與網路、設施及音訊-視覺小組合作，以確保符合部署需求，且每個網站和會議空間在電源和網路方面已準備就緒。

我們針對Teams網站的建議為：

- 專用資源帳戶
- 電源 (面板通常支援 Power over 乙太網路 (PoE+) 電源。 請參閱 OEM 檔，以尋找任何裝置特定的電源需求。) 


有關實體安裝考慮，請參閱 OEM 檔，如果您有，請參閱安裝及安裝裝置及執行纜線連接之前，使用音訊-視覺小組的體驗。

## <a name="configuration-and-deployment"></a>組組和部署

組組和部署規劃涵蓋下列主要領域：

- 資源帳戶資源配置
- 測試

### <a name="resource-account-provisioning"></a>資源帳戶資源配置

每個Teams面板裝置都需要Microsoft 365會議室資源帳戶。 您可以使用資源帳戶認證Microsoft Teams面板裝置上的應用程式。

若要設定 Microsoft 365面板Teams資源帳戶，我們建議您購買[Microsoft Teams 會議室 授權](#license-requirement)。 若要瞭解如何建立資源帳戶並指派授權給資源帳戶，請參閱使用 Microsoft 365 系統管理中心 建立[資源Microsoft 365 系統管理中心。](resource-account-ui.md)

> [!NOTE]
>
>- 如果您已經針對要安裝面板的會議空間設定會議室資源帳戶，請使用相同的會議室資源帳戶來登錄面板裝置。 不過，請確定會議室資源帳戶Microsoft Teams 會議室已指派標準授權，才能使用它做為面板資源帳戶。
>
>- 如果您已經將Microsoft Teams 會議室部署在要安裝 Teams 面板的會議空間中，則不需要購買另一個授權來部署面板。 系統管理員以與主機相同的認證，以相同的認證Microsoft Teams 會議室同一個空間的面板裝置。
>
>- 對於大型會議空間 ，例如會議室或會議室，有多個入口，您可以在每個入口安裝一個面板裝置。 屬於單一會議空間的多個面板會共用相同的資源帳戶，並使用相同的認證來登錄。 您不需要為相同空間的每個面板建立個別的資源帳戶。

> [!TIP]
> 建議您在實際安裝面板之前先建立資源Teams帳戶。
> 請考慮為面板資源帳戶Teams命名慣例。 讓資源帳戶的顯示名稱Microsoft 365描述性且容易理解。 這些名稱是使用者在搜尋會議空間時，在排程會議時，Outlook或Teams的名稱。

### <a name="testing"></a>測試

部署面板之後，您應該測試這些面板。 檢查面板[支援的功能Teams部署](#features-supported-by-teams-panels)裝置上是否正常使用。 請嘗試透過電腦中的 Teams 或 Outlook 365，為各種時段建立數個會議。 檢查面板是否正確顯示排定會議的會議詳細資料與可用性。 請嘗試 **使用保留按鈕** 來檢查您是否可以直接從裝置保留可用的會議空間。

## <a name="manage-teams-panels-in-your-organization"></a>管理Teams的面板

若要管理您的Teams面板裝置，在系統管理中心的左側導Microsoft Teams，請前往裝置Teams ****  >  **面板**。 您可以在這裡變更裝置組調設定檔、管理更新、重新開機裝置、新增和移除裝置標記等。 詳細資訊，請參閱在 Teams[中管理您的Teams。](device-management.md)

## <a name="next-steps"></a>後續步驟

[如何使用Microsoft Teams面板裝置](use-teams-panels.md)

## <a name="see-also"></a>另請參閱

[Microsoft Teams面板上的Teams部落格](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/manage-meeting-space-availability-with-microsoft-teams-panels/ba-p/2167734)

[開始使用Teams面板](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

[Teams面板市集](https://www.microsoft.com/microsoft-teams/across-devices/devices/product?deviceid=815)

[根據面板認證計畫Microsoft Teams認證的裝置](teams-ip-phones.md#currently-certified-teams-panels)
