---
title: 使用 Microsoft 團隊聊天室 Premium 服務的角色式存取控制
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: altsou
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
description: 瞭解 Microsoft 團隊聊天室管理服務的角色式存取控制。
f1keywords: ''
ms.openlocfilehash: 2f3886d7f7f59521028b87f05ffedfaa1fae9ac2
ms.sourcegitcommit: 206e01b72218f57e68823dc23b7ca28bce7cb3bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300287"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>使用 Microsoft 團隊聊天室管理服務的角色型存取控制

在 Microsoft 團隊聊天室管理服務中 (RBAC) 的角色式存取控制可協助您管理使用者對組織中的聊天室資源資料的存取權。 透過指派角色給您的服務入口網站使用者，您可以限制他們可以查看和變更的專案。 每個角色都有一組許可權，決定擁有該角色的使用者可以在貴組織記憶體取及變更哪些使用者。

若要建立、編輯或指派角色，您的帳戶必須具備下列其中一項許可權：

- 全域管理員（透過 Azure Active Directory (Azure AD) 
- 透過 Microsoft 團隊聊天室管理的服務入口網站管理的服務管理員

## <a name="what-is-a-role"></a>何謂角色？

角色定義授與指派給該角色之使用者的一組許可權。 目前，Microsoft [小組聊天室] 管理服務有三個內建角色： **受管理的服務系統管理員**、 **網站主管**和 **網站技術**。 它們涵蓋貴組織中可能涉及管理您的聊天室的使用者的一些常見案例。

若要查看角色，請在 Microsoft 團隊聊天室 managed 服務入口網站的左側導覽中，移至 [ **角色**]，然後選取任何角色，即可查看角色的屬性、許可權和作業。  

- [**屬性**]：名稱、角色類型及描述
- **許可權**：列出角色有權存取的功能和許可權等級。
- **作業**：角色指派的清單，定義哪些使用者擁有房間資源帳戶範圍的設定許可權。 角色可以有多個作業，而使用者可以有多個作業。

## <a name="built-in-roles"></a>內建角色

您可以將內建角色指派給群組或使用者，而無需進一步設定。 請記住，您無法刪除或編輯內建角色的名稱、描述、類型或許可權。

- **Managed Services 系統管理員**：擁有 Microsoft 團隊聊天室 Premium 服務入口網站的完整存取權。
- **網站領導**：組織工作室、存取報表並可管理票證。 無法重設註冊金鑰或變更服務的設定。  
- **網站技術**：管理特定房間的票證。 沒有許可權可以修改服務或管理服務中的聊天室。

下表摘要列出每個角色所能執行的動作。

|功能 |拒絕 |Managed Services 系統管理員  |網站領導  |網站技術  |
|---------|---------|---------|---------|---------|
|教室     |檢視        |&#10004;           |&#10004;           |&#10004;  |
|    |修改         |&#10004;           |&#10004;           |&#10004; |
|    |重設金鑰         |&#10004;           |         ||
|    |下載金鑰         |&#10004;           |&#10004;          |&#10004; |
|    |取消         |&#10004;           |&#10004;           |&#10004; |
|群組管理   |建立         |&#10004;           |           ||
|    |檢視       |&#10004;          |&#10004;           ||
|    |修改         |&#10004;           |           ||
|更新振鈴管理    |建立         |&#10004;           |           ||
|    |檢視         |&#10004;           |           ||
|    |修改         |&#10004;           |           ||
|有關   |檢視        |&#10004;           |&#10004;           ||
|票證管理   |建立客戶事件         |&#10004;           |&#10004;           |&#10004;  |
|    |檢視         |&#10004;           |&#10004;           |&#10004;  |
|    |時更新         |&#10004;           |&#10004;           |&#10004;  |
|Microsoft 團隊聊天室 managed services 設定    |檢視         |&#10004;           |         ||
|    |修改        |&#10004;           |         ||
|角色管理    |檢視         |&#10004;           |         ||
|    |修改         |&#10004;           |         ||

## <a name="assign-a-role"></a>指派角色

若要指派角色，您必須是全域管理員或受管理的服務系統管理員。

1. 在 Microsoft 團隊聊天室 managed 服務入口網站的左側導覽中，移至 [**設定**  >  **角色**]。

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="顯示角色之 [存取控制] 頁面的螢幕擷取畫面":::

2. 選取您要指派的角色。
3. 在 [角色] 窗格中，選取 [**作業**  >  **新增**]。

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="新增角色的 [新增] 選項的螢幕擷取畫面。":::

4. 在 [ **一般設定** ] 頁面上的 [ **作業屬性**] 底下，輸入此工作分派的名稱。 描述是選擇性的。 選擇 **[下一步]。**
5. 在 [ **成員** ] 頁面上，于 [ **搜尋使用者或安全性群組** ] 方塊中，輸入您要授與許可權的租使用者或安全性群組的名稱，然後完成選取專案。 選擇 **[下一步]**。 
6. 在 [ **範圍** ] 頁面上的 [ **搜尋聊天室或聊天室群組** ] 方塊中，輸入可允許使用者管理的聊天室或聊天室群組的名稱。 選擇 **[下一步]**。
7. 在 [ **完成]** 頁面上，查看作業的詳細資料。 如果您對設定感到滿意，請選擇 [ **新增作業**]。 如果您想要編輯節，請使用 [ **上一個** ] 按鈕，或選取左側導覽中的步驟。  

## <a name="related-topics"></a>相關主題

- [Microsoft 團隊聊天室管理的服務](microsoft-teams-rooms-premium.md)
