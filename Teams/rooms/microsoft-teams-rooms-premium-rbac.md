---
title: 使用會議室服務Microsoft Teams角色進階版存取控制
author: dstrome
ms.author: dstrome
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
description: 瞭解使用受管理服務Microsoft Teams 會議室存取控制。
f1keywords: ''
ms.openlocfilehash: c73ad1385a0654f3ef50dab46b803debe418b834b6497acfcb27f5a4de736f98
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301059"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>使用受管理服務的角色Microsoft Teams 會議室存取控制

在受管理的服務 (RBAC) 中Microsoft Teams 會議室角色式存取控制可協助管理使用者對貴組織中會議室資源資料的存取權。 將角色指派給服務入口網站使用者，您可以限制他們可以看到和變更的內容。 每個角色都有一組許可權，可決定哪些具有該角色的使用者可以在貴組織中存取和變更。

若要建立、編輯或指派角色，您的帳戶必須具有下列其中一項許可權：

- 透過 Azure AD Azure Active Directory (全域系統管理員) 
- 透過受管理的服務入口網站Microsoft Teams 會議室服務管理員

## <a name="what-is-a-role"></a>什麼是角色？

角色會定義指派給該角色的使用者所授予的許可權集。 目前，受Microsoft Teams 會議室服務有三個內建角色：Managed **Service 系統管理員**、**網站潛在客戶** 和 **網站技術**。 它們涵蓋組織中可能參與管理您會議室的一些常見案例。

若要查看角色，請在 Microsoft Teams 會議室 管理服務入口網站左側流覽中，前往角色，然後選取任何角色以查看角色的屬性、許可權和指派。  

- **屬性**：名稱、角色類型和描述
- **許可權**：列出角色有權存取的功能和許可權等級。
- **工作** 分派：角色指派清單，定義哪些使用者擁有會議室資源帳戶範圍的已配置許可權。 角色可以有多個工作分派，而使用者可以有多個工作分派。

## <a name="built-in-roles"></a>內建角色

您可以指派內建角色給群組或使用者，而不進行進一步配置。 請記住，您無法刪除或編輯內建角色的名稱、描述、類型或許可權。

- **Managed Service 系統管理員**：擁有會議室Microsoft Teams服務進階版的完整存取權。
- **網站潛在客戶**：整理會議室、存取報表，以及管理票證。 無法重設註冊金鑰，或變更服務的設定。  
- **網站技術**：管理特定會議室的票證。 沒有修改服務或整理服務中聊天室的許可權。

下表摘要列出每個角色可以執行哪些工作。

|功能 |許可 |Managed Service 系統管理員  |網站潛在客戶  |網站技術  |
|---------|---------|---------|---------|---------|
|房間     |檢視        |&#10004;           |&#10004;           |&#10004;  |
|    |修改         |&#10004;           |&#10004;           |&#10004; |
|    |重設按鍵         |&#10004;           |         ||
|    |下載金鑰         |&#10004;           |&#10004;          |&#10004; |
|    |取消註冊         |&#10004;           |&#10004;           |&#10004; |
|群組管理   |創建         |&#10004;           |           ||
|    |檢視       |&#10004;          |&#10004;           ||
|    |修改         |&#10004;           |           ||
|更新響鈴管理    |創建         |&#10004;           |           ||
|    |檢視         |&#10004;           |           ||
|    |修改         |&#10004;           |           ||
|報告   |檢視        |&#10004;           |&#10004;           ||
|票證管理   |建立客戶事件         |&#10004;           |&#10004;           |&#10004;  |
|    |檢視         |&#10004;           |&#10004;           |&#10004;  |
|    |更新         |&#10004;           |&#10004;           |&#10004;  |
|Microsoft Teams 會議室服務設定    |檢視         |&#10004;           |         ||
|    |修改        |&#10004;           |         ||
|角色管理    |檢視         |&#10004;           |         ||
|    |修改         |&#10004;           |         ||

## <a name="assign-a-role"></a>指派角色

若要指派角色，您必須是全域系統管理員或 Managed Service 系統管理員。

1. 在受管理服務入口網站左側Microsoft Teams 會議室，**請前往** 設定  >  **角色**。

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="顯示角色的 Access 控制項頁面螢幕擷取畫面":::

2. 選取您想要指派的角色。
3. 在角色窗格中，選取指派  >  **新增**。

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="新增角色選項的螢幕擷取畫面。":::

4. 在一 **般設定** 頁面的作業 **屬性** 下，輸入此作業的名稱。 描述為選擇性。 選擇 **下一步。**
5. 在成員 **頁面上** 的搜尋使用者或安全性群組方塊中，輸入您租使用者中要提供許可權的使用者或安全性群組名稱，然後完成選取專案。 選擇下 **一個**。 
6. 在範圍 **頁面上** 的搜尋會議室或會議室群組方塊中，輸入允許使用者管理的會議室或會議室群組名稱。 選擇下 **一個**。
7. 在完成 **頁面上** ，查看作業詳細資料。 如果您對組組感到滿意，請選擇新增 **作業**。 如果您想要編輯節，請使用上一 **個按鈕，** 或選取左側導圖中的步驟。  

## <a name="related-topics"></a>相關主題

- [Microsoft Teams 會議室管理服務](microsoft-teams-rooms-premium.md)
