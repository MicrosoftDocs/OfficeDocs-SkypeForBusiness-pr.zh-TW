---
title: 使用應用程式建立資源Microsoft 365 系統管理中心
description: 如果您想要使用圖形使用者介面，您可以使用中心為Microsoft Teams 會議室和共同Microsoft Teams建立資源Microsoft 365 系統管理帳戶。
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: 建立裝置帳戶、Microsoft 365 UI、Microsoft 365 系統管理中心
ms.sitesec: library
ms.service: msteams
author: cazawideh
ms.author: czawideh
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1d4d3a24222183c8798bb5d0e7eda879acca8d3e
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503940"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 建立資源Microsoft 365 系統管理中心

Microsoft 365資源帳戶是專門Teams資源 ，例如會議室、投影機等的信箱和信箱帳戶。 這些資源帳戶可以使用您建立會議邀請時定義的規則，自動回應會議邀請。 例如，如果您有一般資源 ，例如會議室，您可以為會議室設定資源帳戶，根據會議室的日曆可用性，自動接受或拒絕會議邀請。

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>授權

在建立資源Microsoft 365帳戶之前，請檢查其所需的授權類型。 如果您只會使用資源帳戶預約資源 (，請邀請資源加入您的會議，並自動接受或拒絕邀請) ，則不需要指派授權給資源帳戶。 您必須在下列情況下指派授權給資源帳戶：

- **Teams** 會議 如果您希望資源 (例如 Microsoft Teams 會議室 主機、共同合作欄等) 加入 Teams 會議，讓出席者可以透過會議來展示視音訊，您需要 會議室 授權。 
- **PSTN 通話** 如果您希望資源撥打或接聽外部電話號碼 (稱為公用交換電話網絡或 PSTN 通話) ，您需要Microsoft 365 電話系統或Microsoft 365 商務語音授權。

若要進一會議室、電話系統商務語音授權，請參閱Microsoft Teams[附加元件授權](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>在 Microsoft 365 系統管理中心

1. 請流覽以Microsoft 365帳戶https://admin.microsoft.com
2. 為您的租使用者提供Microsoft 365認證。 這會將您帶至您的Microsoft 365 系統管理中心。

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 系統管理中心。":::
3. 在系統管理中心中，流覽至左側面板中的資源 (您可能需要選取顯示所有第一個) ，然後選取會議室&**設備**。

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 系統管理中心 - 資源。":::
4. 選取 **新增資源信箱** 以建立新的會議室帳戶。 輸入帳戶的顯示名稱和電子郵件地址，**選取新增，****然後選取關閉**。 我們建議您將所有資源帳戶的命名慣例標準化。

> [!NOTE]
> 根據預設，資源帳戶會設定為下列設定。 如果您想要變更，請在選取關閉之前，先選取設定排 **程選項**。 如果您想要稍後變更，請流覽至 **ResourcesRooms**  >  **&設備**，選取資源帳戶，然後選取在預約選項下 **編輯**。
>
> - 允許重複會議
> - 自動拒絕下列限制以外的會議
>   - 預約視窗 (天) ：180
>   - 最長 (小時) ：24
> - 自動接受會議邀請

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 系統管理中心 - 新增資源。":::
5. 流覽 **至系統管理** 中心的使用者區段，並在活動使用者清單中，看到您剛剛建立聊天室。

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 系統管理中心 - 查看使用中使用者。":::
6. 選取會議室名稱，右側會顯示帳戶屬性面板。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 系統管理中心 - 使用者屬性。":::
7. 現在您需要為資源帳戶指派密碼。 在面板中，您可以看見帳戶屬性和數個選擇性動作。 選取使用者 **名稱下的** 重設密碼鍵圖示以變更密碼。 取消選擇 **：要求此使用者第一次登出時變更密碼**。 無法透過裝置登錄程式變更密碼。 選取 **重設**。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 系統管理中心 - 重設密碼。":::
8. In the **Licenses and Apps** section, set **Select location** to the country or region where the device will be installed. 向下卷起並選取要指派之授權旁的方塊 ，例如 會議室 ，然後選取儲存 **變更**。 授權可能會視貴組織而異。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 系統管理中心 - 指派授權。":::
