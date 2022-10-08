---
title: 建立會議室和共用 Teams 裝置的資源帳戶
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 請閱讀本文，瞭解如何建立會議室和共用裝置的資源帳戶，包括Microsoft Teams 會議室、Surface Hub 上的Teams 會議室，以及 Teams 的快捷方式顯示器。
ms.openlocfilehash: 1448496137088ce04dc087825e67f7d8b31afd80
ms.sourcegitcommit: 3ad7b46e31890fba7abe739138cd49527d5ca6b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/05/2022
ms.locfileid: "68475495"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>建立及設定會議室和共用 Teams 裝置的資源帳戶

本文提供針對共用空間和裝置建立資源帳戶的步驟，其中包含在 Windows 上設定Microsoft Teams 會議室的資源帳戶、在 Android 上Teams 會議室、在 Surface Hub 上Teams 會議室，以及在 Teams 顯示器上設定快捷方式的步驟。

Microsoft 365 資源帳戶是專用於特定資源的信箱和 Teams 帳戶，例如會議室或投影機。 這些資源帳戶可以使用您在建立時定義的規則自動回應會議邀請。 例如，如果您有會議室等一般資源，您可以為該會議室設定資源帳戶，該會議室會根據其行事曆可用性自動接受或拒絕會議邀請。 

每個資源帳戶在單一Microsoft Teams 會議室安裝或 Teams 顯示快捷方式實作中都是唯一的。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> 如果使用 Microsoft Teams 面板，Teams 會議室資源帳戶會同時登入Teams 會議室和關聯的 Teams 面板。

> [!NOTE]
> **商務用 Skype** <br><br>
> 如果您需要啟用資源帳戶來處理商務用 Skype，請參閱[使用 商務用 Skype Server 部署Microsoft Teams 會議室](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>開始之前

### <a name="requirements"></a>需求

視您的環境而定，您需要一或多個角色才能建立資源帳戶。

|**環境**|**必要角色**|
|-----|-----|
|Azure Active Directory  <br/> |全域系統管理員或使用者系統管理員  <br/> |
|Active Directory  <br/> |Active Directory 企業版系統管理員、網域系統管理員或具有建立使用者的委派許可權。 Azure Active Directory Connect 同步處理許可權。  <br/> |
|Exchange Online  <br/> |全域系統管理員或 Exchange 系統管理員   <br/> |
|Exchange Server  <br/> |Exchange 組織管理或收件者管理   <br/> |

如果您要為Teams 會議室建立資源帳戶，UPN 必須符合資源帳戶的 SMTP 位址。 部署Teams 會議室之前，請參閱[Microsoft Teams 會議室需求](requirements.md)。

### <a name="what-license-do-you-need"></a>您需要什麼授權？

[!INCLUDE [mtr-device-config-license-include](../includes/mtr-device-config-license-include.md)]

## <a name="create-a-resource-account"></a>建立資源帳戶

[!INCLUDE [mtr-device-config-account-include](../includes/mtr-device-config-account-include.md)]

## <a name="configure-mailbox-properties"></a>設定信箱屬性

[!INCLUDE [mtr-device-config-mailbox-include](../includes/mtr-device-config-mailbox-include.md)]

## <a name="turn-off-password-expiration"></a>關閉密碼到期

[!INCLUDE [mtr-device-config-password-include](../includes/mtr-device-config-password-include.md)]

## <a name="assign-a-meeting-room-license"></a>指派會議室授權

[!INCLUDE [mtr-device-config-assign-include](../includes/mtr-device-config-assign-include.md)]

## <a name="next-steps"></a>後續步驟

### <a name="meeting-policies"></a>會議原則

[!INCLUDE [mtr-device-config-policies-include](../includes/mtr-device-config-policies-include.md)]

### <a name="calling"></a>通話

啟用資源帳戶通話沒有唯一的需求。 您啟用資源帳戶的通話方式，與啟用一般使用者的方式相同。

> [!NOTE]
> 我們建議您將通話原則指派給裝置資源帳戶，藉此關閉共用裝置的語音信箱。 如需詳細資訊，請參閱 [Teams 中的通話和來電轉接](../teams-calling-policy.md) 。

[!INCLUDE [mtr-device-config-calendar-include](../includes/mtr-device-config-calendar-include.md)]

## <a name="related-articles"></a>相關文章

[設定Microsoft Teams 會議室帳戶](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)

[部署 Microsoft Teams 會議室](rooms-deploy.md)

[管理 Microsoft Teams 會議室](rooms-manage.md)

[Microsoft Teams 會議室授權](rooms-licensing.md)
