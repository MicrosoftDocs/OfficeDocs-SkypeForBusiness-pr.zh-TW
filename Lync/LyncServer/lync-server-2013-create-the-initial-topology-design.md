---
title: Lync Server 2013： 建立初始拓撲設計
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
ms.openlocfilehash: c6e679b909fbc6b539e173e98f033a771929893c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>建立初始拓撲設計的 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

當您完成安裝 Lync Server 2013 規劃工具之後, 您準備好要開始規劃工具，並開始設計建議的 Lync Server 2013 基礎結構。

<div>


> [!NOTE]  
> 規劃工具是精靈驅動的工具與詳細的指南，以通知您在設計您的網站和拓樸的決策程序。 本主題旨在不太詳盡快顯功能表中，但只是要幫助您開始使用規劃工具設計工作階段中。



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>若要開始使用規劃工具，並建立初始設計

1.  啟動 Lync Server 2013 規劃工具： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**規劃工具**。

2.  開始規劃工具後，便會出現 [**歡迎使用 Microsoft Lync Server 2013 規劃工具**] 頁面。 選擇下列其中一個下列選項來開始設計：
    
      - **選項 1： 開始**   按一下**開始**提供特定的一系列採訪問題與相關選項來定義的準則。 完成初始**開始**面試] 區段中之後，您在繼續進行來定義網站架構**設計站台**。 若要完成此選項，繼續進行步驟 3。
    
      - **選項 2： 設計站台**   [歡迎] 頁面上，按一下**設計站台**會略過 [**開始**] 區段中所述的採訪問題。 會藉由回應**快速入門**] 區段中的採訪問題收集的資訊設為使用此選項的預設值。 按一下 [**設計站台**，資深的設計師可以略過初始採訪，且預設值，視需要變更，在**中央網站**的 [開始] 畫面。 若要完成此選項，略過步驟 3-5，開始執行步驟 6。
    
      - **選項 3： 顯示您儲存拓撲**   如果您已完成並儲存到先前使用規劃工具的拓撲，您可以略過大部分的步驟，並藉由開啟並顯示拓樸開始。 您可以也對拓撲進行的變更和更新，重新儲存它，然後將它匯出至 Microsoft Excel 或 Microsoft Visio。 若要完成此選項，略過步驟 3-12，開始執行步驟 13。

3.  按一下 [開始設計您的 Lync Server 2013 拓撲的 [**開始**]。

4.  藉由選取適當的條件，對您的設計，回答每一節，然後按一下 [**下一步**] 精靈的下一頁繼續。 按一下 [**上一步**之前的頁面上進行變更。
    
    <div>
    

    > [!TIP]  
    > 每一頁有選取準則，並根據慣用的作法和容量規劃的建議的描述。 如果您需要額外的詳細資訊，請按一下 [<STRONG>更多的了解</STRONG>讀取在 Microsoft TechNet 網站上的 Lync Server 2013 規劃文件的詳細的資訊。 您必須具有網際網路連線能力存取 Microsoft TechNet 網站。

    
    </div>

5.  選取您的設計的適當選項。 初始的準則定義之後，頁面會確認完成功能概觀。

6.  按一下 [**設計站台**來定義您的中央網站。
    
    <div>
    

    > [!NOTE]  
    > 每個 Lync Server 2013 拓撲會有至少一個中央網站。 單一中央站台、 中央網站與分支網站數目、 中央網站數目、 或與每個中央網站相關聯的分公司站台的中央網站的數目，可能需要您的設計。

    
    </div>

7.  在 [**網站名稱**] 中，輸入會識別此中央網站的名稱。

8.  在**網站位於使用者**]，輸入預期的內部並行使用者將會位於此中央網站的數目。

9.  在**雲端位於使用者**]，輸入預期線上並行使用者將會位於此中央網站的數目。

10. 視需要修改線上共同作業、 使用者、 語音、 其他部署選項，或伺服器應用程式] 選項。
    
    <div>
    

    > [!IMPORTANT]  
    > 此時在設計中，您可以只選取或清除選項為您的部署。 不過，您可以在稍後階段中規劃工具的設定更多選項]。 也有無法使用，無法清除選項。 此外，您可能必須清除以清除另一個選項。 例如，如果您同時清除下語音，然後<STRONG>回應群組</STRONG>，<STRONG>宣告</STRONG>的<STRONG>Enterprise Voice</STRONG>選項和<STRONG>通話駐留</STRONG>（它們都是企業語音功能） 的伺服器應用程式] 之下的選項也會取消選取。

    
    </div>

11. 定義站台名稱和使用者數量後, 按一下 [**下一步**]。

12. 下列頁面詢問資訊的 SIP 網域、 會議設定、 語音設定和基礎結構、 Exchange UM、 外部使用者存取、 常設聊天室設定、 用戶端設定、 組合的選項，以及分支站台。 回答這些問題，視。

13. 最後一個問題會要求您若要建立另一個中央網站。 如果您選取 [**是**]，然後規劃工具傳回中央網站] 頁面上。 如果您選取 [**否]**，按一下 [**下一步**，，，然後按一下 [先顯示的高層級的全域拓撲檢視**繪製**。

14. 若要檢視現有的拓樸，按一下 [**顯示**]。

15. 按一下表示之前儲存的拓撲的.xml 檔案，然後按一下 [**開啟**。

16. 規劃工具會顯示 [全域拓撲] 頁面。 您現在可以開始編輯、 更新或使用規劃工具中可用的工具來變更拓樸。

</div>

<div>

## <a name="see-also"></a>另請參閱


[編輯 Lync Server 2013 中的設計](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

