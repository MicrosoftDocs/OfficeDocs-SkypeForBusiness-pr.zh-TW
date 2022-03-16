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
ms.localizationpriority: medium
description: 本文提供一個概觀，以及由Microsoft Teams支援的功能。
ms.openlocfilehash: b860b141cddddbb90ce9d28d7895cf385c77c0ff
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514738"
---
# <a name="microsoft-teams-panels"></a>Microsoft Teams面板

Microsoft Teams面板是安裝在會議空間外部的精簡觸控螢幕裝置，通常位於入口旁邊。 Teams面板，您可以一目了然地查看位置和會議詳細資料，並保留現場可用的會議空間。 您可以使用豐富的大型文字和色彩編碼標記，從遠處查看會議空間的可用性。

Teams面板是專用的Microsoft Teams裝置，可顯示透過 Teams 或 Outlook 365 日曆應用程式排定的會議詳細資料。 當會議詳細資料醒目顯示時，出席者可以確認他們位於正確的會議空間、正確的時間，以及適合的會議。

本文提供面板Teams概觀，並可協助規劃、傳遞及管理Teams裝置。

## <a name="features-supported-by-teams-panels"></a>由Teams支援的功能

Teams面板支援下列功能：

- **會議空間和會議詳細資料專用的顯示。** 您可以快速取得會議空間的詳細資訊，包括會議空間的位置和可用性。 對於保留的會議空間，您可以查看重要的會議詳細資料，例如會議標題、會議排程和會議召集人。
- **為臨時會議保留可用的會議空間。** 您可以使用觸控螢幕面板，于當場為臨時會議保留可用的會議空間，然後從Teams裝置或裝置Microsoft Teams 會議室Surface Hub會議。
- **空間可用性狀態的色彩編碼標記。** 您可以使用生動的 LED 和主畫面指示器，近距離查看會議空間的可用性。 綠色表示會議空間可供使用，如有需要，您可以從面板本身保留會議空間。 紅色或紫色表示已保留會議空間。
- **自訂牆紙和保留狀態指示器。** 管理員可以透過設定變更面板的預設面板。 例如，系統管理員可以變更背景牆紙，或變更忙碌狀態指示器的色彩。
- **協助工具。** Teams面板有幾個協助工具功能，例如高對比文字，讓任何人都能更輕鬆地使用這些功能。

若要深入瞭解這些功能及如何使用這些功能，請參閱使用Microsoft Teams[面板](use-teams-panels.md)。

## <a name="partners-certified-for-teams-panels"></a>合作夥伴已Teams面板

若要深入瞭解合作夥伴已認證Teams面板，請參閱[目前認證的Teams面板](teams-ip-phones.md#certified-teams-panels)。

## <a name="teams-panels-requirements"></a>Teams面板需求

部署面板裝置的硬體、軟體和網路需求可能會根據您部署的面板裝置類型而不同。 請參閱原始設備製造商 (OEM) 檔，瞭解一組裝置所需的功能。

## <a name="license-requirement"></a>授權需求

若要使用Teams面板，您需要授權[Microsoft Teams 會議室標準版授權](../rooms/rooms-licensing.md)。

> [!Note]
> 如果您已經將Microsoft Teams 會議室部署在要安裝 Teams 面板的會議空間中，則不需要額外的授權Teams面板。

## <a name="deploy-teams-panels-devices"></a>部署Teams面板裝置

如果您參與規劃、部署及管理Teams面板裝置，則本節適用于您。 此區段並不適合這些面板的Teams使用者。

部署Teams面板裝置可以細分為下列工作：

- [會議空間庫存與功能規劃](#inventory-sites-and-meeting-spaces)：建立貴組織網站與會議空間的庫存，以部署Teams裝置。
- [採購](#procurement)：從所選裝置合作夥伴購買裝置。  
- [網站就緒](#site-readiness)：確認您的部署位置 (會議) 符合部署需求。
- [組配置與部署](#configuration-and-deployment)：建立資源帳戶，並將其指派給裝置。

## <a name="inventory-sites-and-meeting-spaces"></a>庫存網站和會議空間

盤點組織中現有的可預約會議空間。 識別在面板中部署範圍中的網站Teams空間。 請和您的裝置和音訊-視覺小組合作，決定在何處以及如何安裝 Teams 面板裝置，以及安裝面板是否還需要任何其他硬體。

## <a name="procurement"></a>採購

根據在面板中部署Teams的會議空間數量，請從其中一個經過認證的合作夥伴取得Teams[裝置](#partners-certified-for-teams-panels)。 請流覽合作夥伴的網站，深入瞭解裝置和採購選項。

貴組織的會議空間對於安裝或安裝裝置的硬體需求可能不同。 例如，將裝置安裝在玻璃、灰灰、幹牆或木材面板上所需的硬體可能不同。 請參閱裝置合作夥伴的檔，以尋找可用的安裝選項。

## <a name="site-readiness"></a>網站準備就緒

當訂購的裝置傳送給貴組織時，請與網路、設施及音訊-視覺小組合作，以確保符合部署需求，且每個網站和會議空間在電源和網路方面已準備就緒。

我們針對Teams網站的建議為：

- 專用資源帳戶
- 電源 (面板通常支援 Power over 乙太網路， (PoE+) 電源。 請參閱 OEM 檔，以尋找任何裝置特定的電源需求。) 


有關實體安裝考慮，請參閱 OEM 檔，如果您有，請參閱安裝及安裝裝置及執行纜線連接前，先使用音訊-視覺小組的體驗。

## <a name="configuration-and-deployment"></a>組配置與部署

組配置與部署規劃涵蓋下列主要領域：

- 資源帳戶資源配置
- 測試

### <a name="resource-account-provisioning"></a>資源帳戶資源配置

每個Teams面板裝置都需要Microsoft 365會議室資源帳戶。 您可以使用資源帳戶認證來Microsoft Teams面板裝置上的應用程式。

若要設定Microsoft 365面板Teams資源帳戶，建議您購買Microsoft Teams 會議室標準版[授權](#license-requirement)。 若要瞭解如何建立資源帳戶並指派授權給資源帳戶，請參閱為會議室建立資源帳戶，以及Teams[共用](../rooms/with-office-365.md)。

> [!NOTE]
>
>- 如果您已經針對要安裝面板的會議空間設定會議室資源帳戶，請使用相同的會議室資源帳戶來登錄面板裝置。 不過，請確定會議室資源帳戶Microsoft Teams 會議室標準版指派授權，才能使用它做為面板資源帳戶。
>
>- 如果您已經將 Microsoft Teams 會議室部署在安裝 Teams 面板的會議空間中，則不需要購買另一個授權來部署面板。 系統管理員以與同一個共用空間相同的認證Microsoft Teams 會議室面板裝置。
>
>- 對於大型會議空間 ，例如會議室或會議室，有多個入口，您可以在每個入口安裝一個面板裝置。 屬於單一會議空間的多個面板會共用相同的資源帳戶，並使用相同的認證來登錄。 您不需要為相同空間的每個面板建立個別的資源帳戶。

> [!TIP]
> 建議您在實際安裝面板之前先建立資源Teams帳戶。
> 請考慮為面板資源帳戶使用Teams慣例。 讓資源帳戶的顯示Microsoft 365描述性且容易理解。 這些名稱是使用者在搜尋會議空間時，在Outlook或Teams看到的名稱。

### <a name="testing"></a>測試

部署面板之後，您應該測試這些面板。 檢查面板[支援的功能](#features-supported-by-teams-panels)Teams部署裝置上是否正常使用。 請嘗試透過電腦中的 Teams 或 Outlook 365，為不同的時段建立數個會議。 檢查面板是否正確顯示排定會議的會議詳細資料與可用性。 請嘗試 **使用保留按鈕** 來檢查您是否可以直接從裝置保留可用的會議空間。

## <a name="manage-teams-panels-in-your-organization"></a>管理Teams的面板

若要管理您的Teams面板裝置，在系統管理中心的左側導Microsoft Teams，請前往 Teams **窗格**  >  。**** 您可以在這裡變更裝置組調設定檔、管理更新、重新開機裝置、新增和移除裝置標記等等。 詳細資訊，請參閱在 Teams[中管理您的Teams](device-management.md)。

## <a name="next-steps"></a>後續步驟

[如何使用Microsoft Teams面板裝置](use-teams-panels.md)

## <a name="see-also"></a>另請參閱

[Microsoft Teams面板上的Teams部落格](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/manage-meeting-space-availability-with-microsoft-teams-panels/ba-p/2167734)

[開始使用Teams面板](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

[Teams面板市集](https://office.com/teamsdevices)

[根據面板認證計畫Microsoft Teams認證的裝置](teams-ip-phones.md#certified-teams-panels)
