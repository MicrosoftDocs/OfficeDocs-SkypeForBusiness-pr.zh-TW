---
title: 建立商務用 Skype Server 2015 的初始拓撲設計
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: 在您完成商務用 Skype Server 規劃工具的安裝之後，就可以開始規劃工具及開始設計擬議中的商務用 Skype Server 2015 基礎結構。
---

# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>建立商務用 Skype Server 2015 的初始拓撲設計

在您完成商務用 Skype Server 規劃工具的安裝之後，就可以開始規劃工具及開始設計擬議中的商務用 Skype Server 2015 基礎結構。

> [!NOTE]
>  規劃工具是一個嚮導導向工具，具有詳細的指南，可在設計網站和拓撲時通知決策過程。 本主題的目的不是詳盡的指南，只是協助您在設計會話中開始使用規劃工具。

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>開始使用規劃工具及建立初始設計

1. 啟動商務用 Skype Server 2015 規劃工具：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server 2015**]，然後按一下 [**規劃工具**]。

2. 在規劃工具開始之後，就會出現 [**歡迎使用商務用 Skype Server 2015 的規劃工具**] 頁面。 選擇下列其中一個選項來開始您的設計：

   - **選項1：入門** 按一下 **入門** 會提供特定系列的採訪問題，以及相關選擇以定義準則。 完成初始 **入門** 面試區段之後，您可以繼續進行 **設計網站**，以定義網站架構。 若要完成此選項，請繼續進行步驟3。

   - **選項2：設計網站** 按一下 [歡迎] 頁面上的 [**設計網站**]，便不會略過 **入門** 區段中所述的面試問題。 使用此選項，以回應 **入門** 區段中的面試問題來收集的資訊會設定為預設值。 透過按一下 [ **設計網站**]，經驗豐富的設計者可以略過初次面試，並視需要在 [ **中央網站** 開始] 頁面上變更預設值。 若要完成此選項，請略過步驟3-5，並從步驟6開始。

   - **選項3：顯示您儲存的拓撲** 如果您已透過先前使用規劃工具完成並儲存拓撲，您可以略過這些步驟，然後開啟並顯示拓撲。 您也可以對拓撲進行變更和更新，並重新保存，然後將它匯出至 Microsoft Excel 或 Microsoft Visio。 若要完成此選項，請略過步驟3-12，並從步驟13開始。

3. 按一下 [**入門**] 以開始設計您的商務用 Skype Server 2015 拓撲。

4. 請選取您設計的適當準則，然後按 **[下一步** ] 繼續進行下一個嚮導頁面，以回答每一節。 按一下 [ **上一步** ]，在先前頁面上進行變更。

    > [!TIP]
    > 每一頁都有選取準則的描述，以及根據慣用做法和容量規劃的建議。 如果您需要其他詳細資料，請按一下 [**深入瞭解**]，以閱讀 Microsoft 網站上的商務用 Skype Server 2015 規劃檔中的詳細資訊。 您必須具有網際網路連線才能存取 Microsoft 網站。

5. 為您的設計選取適當的選項。 在定義初始準則之後，頁面會確認您的功能概述已完成。

6. 按一下 [ **設計網站** ] 以定義您的中央網站。

    > [!NOTE]
    > 每個商務用 Skype Server 2015 拓朴至少都有一個中央網站。 您的設計可能有單一中央網站、包含許多分支網站的中央網站、許多中央網站，或具有與每個中央網站相關聯之分支網站的中央網站數目。

7. 在 [ **網站名稱**] 中，輸入要識別此中央網站的名稱。

8. 在 [ **網站主使用者**] 中，輸入將裝載于此中央網站中的內部部署並行使用者數目。

9. 在 [ **雲端主使用者**] 中，輸入將位於此中央網站的預期線上並行使用者數目。

10. 視需要，修改線上共同作業、使用者、語音、其他部署選項或伺服器應用程式的選取範圍。

    > [!IMPORTANT]
    > 在設計的此階段，您只可以選取或清除部署的選項。 不過，您可以在規劃工具的後續階段中設定更多選項。 也有無法使用且無法清除的選項。 此外，您可能需要清除其中一個選項，才能清除另一個選項。 例如，如果您清除 [語音] 底下的 [**企業語音**] 選項，則 [伺服器應用程式] 底下的 **回應群組**、**宣告** 及 **通話駐留** 選項，也會同時清除企業語音) 的功能 (。

11. 定義網站名稱和使用者數目後，請按 **[下一步]**。

12. 下列頁面要求有關 SIP 網域、會議設定、語音設定和基礎結構、Exchange UM、外部使用者存取、持續聊天設定、用戶端設定、組合選項及分支網站的資訊。 請視需要回答這些問題。

13. 最後一個問題會詢問您是否要建立另一個中央網站。 如果您選取 **[是]**，則規劃工具會傳回 [中央網站] 頁面。 如果您選取 [ **否**]，請按 **[下一步]**，然後按一下 [ **繪圖** ] 顯示高層級通用拓撲視圖。

14. 若要查看現有的拓撲，請按一下 [ **顯示**]。

15. 按一下代表先前儲存的拓撲的 .xml 檔案，然後按一下 [ **開啟**]。

16. 規劃工具會顯示 [全域拓撲] 頁面。 您現在可以使用規劃工具中提供的工具開始編輯、更新或變更拓撲。

## <a name="see-also"></a>另請參閱

[編輯設計](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)