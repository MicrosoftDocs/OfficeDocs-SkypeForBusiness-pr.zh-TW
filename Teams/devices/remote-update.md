---
title: 遠端Microsoft Teams更新裝置
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 使用 Microsoft Teams中心Teams遠端更新手機、Teams面板和共同Teams橫條圖
ms.openlocfilehash: 4166d8543c0c0e847e4463ecf3cf0760876a7b37
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632177"
---
# <a name="update-microsoft-teams-devices-remotely"></a>遠端Microsoft Teams更新裝置

您可以使用 Microsoft Teams 系統管理中心，遠端更新 Teams 裝置，例如 Teams 手機、Teams 面板和共同合作橫條圖，您也可以選擇裝置固件自動更新行為。 您可以使用系統管理中心在裝置上更新Teams：

- Teams應用程式與團隊系統管理員
- 公司入口網站應用程式
- OEM 代理應用程式
- 裝置固件

裝置固件更新可以自動或排程為未來的日期和時間。 其他可用的裝置更新不會自動申請，但可以手動或排程未來日期和時間。

> [!NOTE]
> 雖然可以排程裝置固件更新，但如果排定的日期和時間落在所配置的最長 30 天或 90 天延遲之後，則當達到最大延遲時間時，即會應用固件更新。 排程的日期和時間會被忽略。 此外，遠端Microsoft Teams裝置是美國政府雲端租使用者 (GCC-高) 。

若要管理裝置，您必須是全域系統管理員、Teams系統管理員，或Teams系統管理員。有關系統管理員角色的資訊，請參閱使用 Microsoft Teams[系統管理員角色來管理Teams。](../using-admin-roles.md)

## <a name="choose-automatic-device-firmware-update-behavior"></a>選擇自動裝置固件更新行為

裝置固件更新會自動使用。 您可以選擇是否要在更新發行後 (于更新發行) 或更新發行後的 30 或 90 天內，于第一個週末申請更新。 根據預設，裝置固件更新會于一次發行後 30 天內使用。

> [!IMPORTANT]
> 您的裝置上不會Teams更新版本。 相反地，您裝置上自動申請的更新會延遲一個版本。 例如，假設您的裝置已採用版本"10"，且版本"11"已發行。 版本 "11" 尚未適用。 相反地，您的裝置只會在版本 "12" 發行後更新為版本 "11"。

> [!NOTE]
> 某些裝置還不支援自動固件更新。 在不支援自動更新的裝置上，將自動更新設定適用于這些裝置並沒有任何影響。 如需您的裝置是否支援自動固件更新的問題，請與您的裝置製造商聯繫。

若要為裝置選擇自動更新行為，請執行下列操作：

1. 請流覽 Microsoft Teams系統 https://admin.teams.microsoft.com 管理中心。
2. 流覽 **裝置**  >  **IP 電話** 或 **共同Teams****面板**。
3. 選取一或多個裝置， **然後選取** 更新 。
4. 在 **固件自動更新下**，選取下列其中一項：
    - **一旦推出** 第二個最新裝置固件更新會于最新更新發行後的第一個週末進行。
    - **延後 30 天** 第二個最新裝置固件更新會于最新更新發行後的 30 天內使用。
    - **延後 90 天** 第二個最新裝置固件更新會于最新更新發行後的 90 天內使用。
5. 選取 **更新**。

如果基於任何原因，您需要還原裝置固件更新，您必須將裝置重設為出廠設定。 使用裝置製造商的指示重設裝置。  

## <a name="manually-update-remote-devices"></a>手動更新遠端裝置

當您使用系統管理中心更新一或多個裝置時，您可以決定是否立即更新裝置，或為未來的日期和時間排程更新。

若要手動更新遠端裝置，請執行下列操作：

1. 請流覽 Microsoft Teams系統 https://admin.teams.microsoft.com 管理中心。
2. 流覽 **裝置**  >  **IP 電話** 或 **共同Teams****面板**。
3. 選取一或多個裝置， **然後選取** 更新 。
4. 如果您想要 **為** 未來的日期和時間排程更新，請選取在手動更新下排程。 更新會以時區中選取的時區日期和時間 **來申請**。

您所看到的內容取決於您已選取一或多個裝置。 下方的左影像顯示已選取多個裝置，而右側影像則顯示已選取的單一裝置。

:::image type="content" source="../media/device-update-status.png" alt-text="裝置更新狀態窗格中的單一和多個裝置視圖":::

當您選取多個裝置時，您可以選擇要適用于每個所選裝置的更新類型。 選取要申請的更新類型， **然後選取** 更新 。

當您選取單一裝置時，會顯示適用于該裝置的更新。 如果裝置可以使用多種更新類型，請選取要申請的每一種更新類型。 您可以查看裝置 **上** 所適用之目前版本， **以及將會採用** 的新版。 選取您想要 (更新) ，然後選取 **更新**。

選取更新 **之後**，更新會在您選取的日期與時間，在您排程更新時，會一併適用于您的裝置。 如果您沒有選取未來的日期和時間，更新會于幾分鐘內適用于您的裝置。
