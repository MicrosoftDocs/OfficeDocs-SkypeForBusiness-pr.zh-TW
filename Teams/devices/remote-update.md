---
title: 遠端更新 Microsoft Teams 裝置
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
localization_priority: Normal
description: 使用 Teams 系統管理中心遠端更新 Microsoft Teams 手機、Teams 面板和共同合作長條
ms.openlocfilehash: 67b76d8330de5a801625a22c25cd1f9637048d05
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347884"
---
# <a name="update-microsoft-teams-devices-remotely"></a>遠端更新 Microsoft Teams 裝置

使用 Microsoft Teams 系統管理中心，您可以遠端更新 Teams 裝置，例如 Teams 手機、Teams 面板和共同合作長條，而且您可以選擇裝置內款的自動更新行為。 您可以使用 Teams 系統管理中心在裝置上更新下列專案：

- Teams 應用程式與 Teams 系統管理員代理程式
- 公司入口網站應用程式
- OEM 代理程式應用程式
- 裝置中

裝置方程式可以自動進行更新，也可以排程為未來的日期和時間。 其他可用的裝置更新不會自動適用，但可以手動或排程于未來的日期和時間。

> [!NOTE]
> 雖然可以排程裝置中的更新，但如果排定的日期和時間落在所配置的最長 30 天或 90 天延遲之後，當達到最大延遲時，即會使用該更新。 排程的日期和時間會被忽略。 此外，遠端更新 Microsoft Teams 裝置是美國政府雲端租使用者 (GCC-High) 。

若要管理裝置，您必須是全域系統管理員、Teams 服務系統管理員或 Teams 裝置系統管理員。有關系統管理員角色的資訊，請參閱使用[Microsoft Teams 系統管理員角色來管理 Teams。](../using-admin-roles.md)

## <a name="choose-automatic-device-firmware-update-behavior"></a>選擇自動裝置新訊更新行為

裝置中會自動使用裝置中的更新。 您可以選擇是否要在更新發行後 (于更新發行後的第一個週末或更新發行後的 30 或 90 天，于) 或 30 天之後，再使用更新。 根據預設，裝置方程式會更新 30 天，一次發行。

> [!IMPORTANT]
> Teams 裝置上不會使用最新的新版更新。 相反地，自動在裝置上所使用更新會延後一個版本。 例如，假設您的裝置已使用版本"10"，且已發行版本本 "11"。 版本 "11" 尚未適用。 相反地，您的裝置只會在版本 "12" 發行後更新為版本 "11"。

> [!NOTE]
> 部分裝置目前不支援自動更新的裝置。 在不支援自動更新的裝置上，將自動更新設定適用于這些裝置並沒有任何影響。 如需裝置是否支援自動更新的相關問題，請與您的裝置製造商聯繫。

若要選擇您裝置自動更新的行為，請執行下列操作：

1. 請流覽以前往 Microsoft Teams 系統管理中心 https://admin.teams.microsoft.com 。
2. 流覽 **裝置**  >  **IP 電話、****共同合作長條** 或 **Teams 面板**。
3. 選取一或多個裝置， **然後選取更新**。
4. 在 **Firmware 自動更新下**，選取下列其中一項：
    - **一旦可用** 最新更新發行後的第一個週末，即會使用第二個最新的裝置更新。
    - **延後 30 天** 第二個最新裝置新訊的更新會于最新更新發行後的 30 天內執行。
    - **延後 90 天** 第二個最新裝置新訊的更新會于最新更新發行後的 90 天內執行。
5. 選取 **更新**。

如果基於任何原因，您需要還原裝置方程式更新，您必須將裝置重設為出廠設定。 使用裝置製造商的指示重設裝置。  

## <a name="manually-update-remote-devices"></a>手動更新遠端裝置

當您使用系統管理中心更新一或多個裝置時，您可以決定是否要立即更新裝置，或排定未來日期和時間的更新。

若要手動更新遠端裝置，請執行下列操作：

1. 請流覽以前往 Microsoft Teams 系統管理中心 https://admin.teams.microsoft.com 。
2. 流覽 **裝置**  >  **IP 電話、****共同合作長條** 或 **Teams 面板**。
3. 選取一或多個裝置， **然後選取更新**。
4. 如果您要 **將更新****排程** 為未來的日期和時間，請在手動更新下選取排程。 更新會于時區中所選時區的 **日期和時間進行。**

您所看到的內容取決於您已選取一或多個裝置。 下圖左側顯示已選取多個裝置，而右邊的影像顯示已選取的單一裝置。

:::image type="content" source="../media/device-update-status.png" alt-text="裝置更新狀態窗格中的單一和多個裝置視圖":::

當您選取多個裝置時，您可以選擇要適用于每個所選裝置的更新類型。 選取要申請的更新類型， **然後選取更新**。

當您選取單一裝置時，會顯示裝置可用的更新。 如果裝置有多個更新類型可用，請選取要申請的每一種更新類型。 您可以查看裝置 **上** 所適用之目前版本，以及要 **申請的** 新版本。 選取要 () 的更新， **然後選取更新**。

選取更新 **之後**，若您已排程更新，更新會在您選取的日期與時間，將更新適用于您的裝置。 如果您未選取未來的日期和時間，更新會于幾分鐘內適用于您的裝置。
