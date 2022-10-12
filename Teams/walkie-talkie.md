---
title: Microsoft Teams 中的無線對講機應用程式
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 如何從 IT 系統管理員的觀點，在 Microsoft Teams 中設定無線對講機應用程式。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0475fd161d3b53a8fc60d3a1419d20e3de2bfada
ms.sourcegitcommit: bb428cd5805151736f0a6786d737f67f2b3fc918
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2022
ms.locfileid: "68557476"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams 中的無線對講機應用程式

Teams 中的 [無線對講機] 應用程式可為您的團隊提供即時推入式 (式 PTT) 通訊，而且可在 Android 和 iOS 上使用。 無線對講機可讓使用者使用屬於其成員的相同基礎頻道與其團隊連線。 只有連線到頻道中無線對講機的使用者會成為參與者，而且可以一次使用一個推播式對講機彼此通訊。

有了 Teams 中的無線對講機，第一線工作人員就可以安全地與熟悉的 PTT 體驗通訊，而不需要攜帶大量無線電，而且無線對講機可以在 WiFi 或行動網路網際網路連線的任何地方使用。

> [!NOTE]
> 中國目前不提供無線對講機。

## <a name="license-requirements"></a>授權需求

Microsoft [365 和 Office 365 訂閱](/office365/servicedescriptions/teams-service-description)的所有 Teams 付費授權都包含無線對講機。 如需取得 Teams 的詳細資訊，請參[閱如何?取得 Microsoft Teams 的存取權？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploying-walkie-talkie"></a>部署無線對講機

搭配 Google Mobile Services (MCS) 和 iOS 裝置的 Android 裝置支援無線對講機。

> [!NOTE]
> 如果您的使用者使用藍牙配件，請確定您的行動裝置管理 (MDM) 解決方案不會封鎖藍牙裝置。

### <a name="enable-or-disable-walkie-talkie-in-your-organization"></a>啟用或停用組織中的無線對講機

根據預設，組織中所有的 Teams 使用者都會啟用無線對講機。 您可以在 Microsoft Teams 系統管理中心的[管理應用程式](manage-apps.md)頁面上關閉或開啟組織層級的應用程式。

1. 在 Teams 系統管理中心的左側導覽中，移至 **[Teams 應用程式]** > **[管理應用程式]**。
2. 在應用程式清單中，搜尋 [無線對講機] 應用程式，選取它，然後將 **[狀態** ] 切換為 [ **已封鎖** ] 或 [ **允許]**。

### <a name="enable-or-disable-walkie-talkie-for-specific-users-in-your-organization"></a>為貴組織中的特定使用者啟用或停用無線對講機

若要允許或封鎖貴組織中的特定使用者使用無線對講機，請確定貴組織已在 [ [管理應用程式](manage-apps.md) ] 頁面上開啟 [無線對講機]。 然後建立自訂應用程式許可權原則、將它新增至應用程式設定原則，然後將它指派給這些使用者。 若要深入瞭解，請參閱 [在 Teams 中管理應用程式許可權原則](teams-app-permission-policies.md) 和 [在 Microsoft Teams 中管理應用程式設定原則](teams-app-setup-policies.md)。

### <a name="pin-walkie-talkie-to-teams"></a>將無線對講機釘選到 Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>使用量身打造的第一線應用程式體驗，將無線對講機和其他應用程式釘選到 Teams

Teams 中量身打造的第一線應用程式體驗可為擁有 [F 授權](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的使用者釘選 Teams 中最相關的應用程式。 釘選的應用程式包括無線對講機、班次、工作和核准。 根據預設，此功能為您的第一線工作人員提供專為其需求量身打造的全新體驗。

應用程式會釘選到應用程式行，也就是 Teams 桌面用戶端側邊和 Teams 行動用戶端底部的列，使用者可以在此快速且輕鬆地存取它們。

若要深入瞭解，包括體驗如何與您所設定的應用程式原則搭配運作，請參閱 [為您的第一線員工量身打造 Teams 應用程式](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>使用應用程式設定原則將無線對講機釘選到 Teams

應用程式設定原則可讓您自訂 Teams，以釘選對使用者中使用者最重要的應用程式。

若要為使用者釘選無線對講機應用程式，您可以編輯全域 (組織的預設) 原則，或建立及指派自訂應用程式設定原則。 若要深入了解，請參閱[管理 Teams 中的應用程式設定原則](teams-app-setup-policies.md)。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="螢幕擷取畫面顯示在 [新增釘選的應用程式] 窗格中，將 [無線對講機] 新增至釘選的應用程式清單。" lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>網路檔

Teams 中的無線對講機需要網際網路連線。 您必須有下列網路條件才能獲得最佳體驗。

|度量 | 必要 |
|---|---|
|RTT)  (延遲 | < 300 ms |
|抖動 |< 30 ms |
|封包遺失 |< 1% |

如上所述，透過 IP 網路即時媒體的品質受到網路連線品質的極大影響，尤其是受以下情況影響：

- **延遲** - 從 A 點取得 IP 封包到網路上指向 B 所需的時間。 此網路傳播延遲基本上是與兩點之間的實體距離和光速系結，包括兩者之間各種路由器所佔用的額外負荷。 延遲是以 RTT)  (來回時間來測量。
- **送達間抖動** - 連續封包之間的延遲平均值變更。
- **封包遺失** - 封包遺失通常是定義為在指定時間範圍中遺失的封包百分比。 封包遺失會直接影響音訊品質，從幾乎沒有影響的小型、個別遺失封包，到造成完整音訊完全中斷的連續中斷。

傳送或接收音訊時，無線對講機的預期資料使用量大約為 20 Kb/s。 閒置時，可忽略無線對講機的預期資料使用量。

## <a name="walkie-talkie-devices"></a>無線對講機裝置

即使在手機遭到鎖定時，第一線工作人員仍需要使用無線對講機通話並接聽電話。 此體驗可透過具有專用 PTT 按鈕的專用裝置來體驗。

#### <a name="headsets"></a>耳機

- iOS 和 Android (無線耳機) 
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Android (有線耳機僅) 
  - [器克電子](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>崎嶇不平的 Android 手機

- 交叉處理 [Core-X4](https://www.crosscall.com/en_FR/core-s4-1004010501053.html)、 [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html)、 [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html)、 [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html)和 [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - 手動設定：安裝 Teams 之後，移至 [**設定**  >  **] 按鈕**。 在 [專用] 按鈕 (1 或 2) ，選取 [ **長按**]，然後選擇 **[PTT 應用程式]**。 選取 [ **自訂]** 旁邊的藍色滾輪，然後選 **取 [Teams]**。
- Kyocera [DuraForce Ultra 5G](https://kyoceramobile.com/duraforce-ultra-5g/) 和 [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - 手動設定：安裝 Teams 之後，移至 [**設定**  >  **程式化] 按鍵**。 根據裝置) ，選擇 **[PTT 鍵** ] 或 [ **按住** 不放 (]，然後選 **取 [Teams]**。
- Honeywell [CT30 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-handheld-computer)、 [CT30 XP HC](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-hc-mobile-computer)、 [CT45 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct45-ct45-xp)、 [EDA51](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/scanpal-eda51-handheld-computer)、 [EDA52](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/eda52-handheld-computer)、 [EDA52 HC](https://sps.honeywell.com/gb/en/products/productivity/mobile-computers/healthcare-computers/scanpal-eda52-healthcare-mobile-computer)、 
  - 手動設定：安裝 Teams 後，依預設專用 PTT 按鈕可與無線對講機搭配使用。
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)， [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy)， [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - 手動設定：安裝 Teams 之後，移至 **[設定****進階**  >  功能  >  **XCover/Active 鍵]**。 開啟 **[搭配應用程式控制 XCover 金鑰]** ，然後選 **取 [Teams]**。
  - [MDM 設定](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - 手動設定：安裝 Teams 之後，移至 **[設定**  >  **程式化金鑰]**。 選擇 **[選取 PTT 鍵應用程式**]，然後選 **取 [Teams]**。
- Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html)、 [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html)、 [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html)、 [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html)、 [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html)、 [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html)、 [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - 手動設定：安裝 Teams 後，依預設專用 PTT 按鈕 (LEFT_TRIGGER_2) 可與無線對講機搭配使用。

> [!NOTE]
> 這些裝置未通過 Teams 認證。 他們已通過驗證，可搭配 Teams 無線對講機使用。

## <a name="more-information"></a>詳細資訊

- 如果您的前線員工使用行動資料透過 Teams 進行通訊，無線對講機會使用相同的方法。
- 無線對講機在頻寬不足或智慧型手機連線正常運作的情況下，應該可以正常運作。 完全沒有連線時，無線對講機就無法運作。

若要深入瞭解使用者體驗，請參閱：

- [開始使用 Teams 無線對講機](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [使用無線對講機與您的小組通訊](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
