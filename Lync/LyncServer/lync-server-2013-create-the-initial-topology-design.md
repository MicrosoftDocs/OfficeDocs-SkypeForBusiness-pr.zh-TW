---
title: Lync Server 2013：建立初始拓撲設計
description: Lync Server 2013：建立初始拓撲設計。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c91bfe68a1de4a1f9862948edd708b8efa6a5c6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551089"
---
# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>建立 Lync Server 2013 的初始拓撲設計

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在您完成安裝 Lync Server 2013 （規劃工具）之後，您就可以開始規劃工具，並開始設計建議的 Lync Server 2013 基礎結構。

<div>


> [!NOTE]  
> 規劃工具是一個嚮導導向工具，具有詳細的指南，可在設計網站和拓撲時通知決策過程。 本主題的目的不是詳盡的指南，只是協助您在設計會話中開始使用規劃工具。



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>開始使用規劃工具及建立初始設計

1.  啟動 Lync Server 2013，規劃工具：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync Server 2013**]，然後按一下 [ **規劃工具**]。

2.  在規劃工具開始之後，即會出現 [ **歡迎使用 Microsoft Lync Server 2013 的規劃工具** ] 頁面。 選擇下列其中一個選項來開始您的設計：
    
      - **選項1：快速入門**    按一下 [**開始**使用] 提供特定系列的採訪問題，以及相關選擇以定義準則。 當您完成最初的「 **入門** 面試」區段之後，請繼續進行 **設計網站** 以定義您的網站架構。 若要完成此選項，請繼續進行步驟3。
    
      - **選項2：設計網站**    按一下 [歡迎] 頁面上的 [**設計網站**]，可以略過「**開始**使用」區段中的 [面試問題]。 使用此選項，以回應「 **開始** 使用」區段中的「面試問題」區段所收集到的資訊將會設定為預設值。 透過按一下 [ **設計網站**]，經驗豐富的設計者可以略過初次面試，並視需要在 [ **中央網站** 開始] 頁面上變更預設值。 若要完成此選項，請略過步驟3-5，並從步驟6開始。
    
      - **選項3：顯示您儲存的拓撲**    如果您已透過先前使用規劃工具完成並儲存拓撲，您可以略過這些步驟，然後開啟並顯示拓撲。 您也可以對拓撲進行變更和更新，並重新保存，然後將它匯出至 Microsoft Excel 或 Microsoft Visio。 若要完成此選項，請略過步驟3-12，並從步驟13開始。

3.  按一下 [ **開始** 著手]，以開始設計 Lync Server 2013 拓撲。

4.  請選取您設計的適當準則，然後按 **[下一步** ] 繼續進行下一個嚮導頁面，以回答每一節。 按一下 [ **上一步** ]，在先前頁面上進行變更。
    
    <div>
    

    > [!TIP]  
    > 每一頁都有選取準則的描述，以及根據慣用做法和容量規劃的建議。 如果您需要其他詳細資料，請按一下 [ <STRONG>深入瞭解</STRONG> ]，以閱讀 Microsoft TechNet 網站上的 Lync Server 2013 規劃檔中的詳細資訊。 您必須具有網際網路連線才能存取 Microsoft TechNet 網站。

    
    </div>

5.  為您的設計選取適當的選項。 在定義初始準則之後，頁面會確認您的功能概述已完成。

6.  按一下 [ **設計網站** ] 以定義您的中央網站。
    
    <div>
    

    > [!NOTE]  
    > 每個 Lync Server 2013 拓撲至少會有一個中央網站。 您的設計可能有單一中央網站、包含許多分支網站的中央網站、許多中央網站，或具有與每個中央網站相關聯之分支網站的中央網站數目。

    
    </div>

7.  在 [ **網站名稱**] 中，輸入要識別此中央網站的名稱。

8.  在 [ **網站主使用者**] 中，輸入將裝載于此中央網站中的內部部署並行使用者數目。

9.  在 [ **雲端主使用者**] 中，輸入將位於此中央網站的預期線上並行使用者數目。

10. 視需要，修改線上共同作業、使用者、語音、其他部署選項或伺服器應用程式的選取範圍。
    
    <div>
    

    > [!IMPORTANT]  
    > 在設計的此階段，您只可以選取或清除部署的選項。 不過，您可以在規劃工具的後續階段中設定更多選項。 也有無法使用且無法清除的選項。 此外，您可能需要清除其中一個選項，才能清除另一個選項。 例如，如果您清除 [語音] 底下的 [ <STRONG>Enterprise Voice</STRONG> ] 選項，則 [伺服器應用程式] 下的 [ <STRONG>回應群組</STRONG>]、[ <STRONG>宣告</STRONG>] 和 [ <STRONG>通話駐留</STRONG> ] 選項會同時清除 [伺服器應用程式] 下的 [ (所有功能]) 。

    
    </div>

11. 定義網站名稱和使用者數目後，請按 **[下一步]**。

12. 下列頁面要求有關 SIP 網域、會議設定、語音設定和基礎結構、Exchange UM、外部使用者存取、持續聊天設定、用戶端設定、組合選項及分支網站的資訊。 請視需要回答這些問題。

13. 最後一個問題會詢問您是否要建立另一個中央網站。 如果您選取 **[是]**，則規劃工具會傳回 [中央網站] 頁面。 如果您選取 [ **否**]，請按 **[下一步]**，然後按一下 [ **繪圖** ] 顯示高層級通用拓撲視圖。

14. 若要查看現有的拓撲，請按一下 [ **顯示**]。

15. 按一下代表先前儲存的拓撲的 .xml 檔案，然後按一下 [ **開啟**]。

16. 規劃工具會顯示 [全域拓撲] 頁面。 您現在可以使用規劃工具中提供的工具開始編輯、更新或變更拓撲。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中編輯設計](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

