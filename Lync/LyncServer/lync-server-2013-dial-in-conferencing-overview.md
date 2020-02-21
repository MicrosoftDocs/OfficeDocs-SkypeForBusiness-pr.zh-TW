---
title: Lync Server 2013 電話撥入式會議概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d088d07e5d49a916835da581af81ff7def581b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的電話撥入式會議概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-30_

如果您的組織有使用者需要參加 Lync Server 2013 內部部署會議，不在辦公室或沒有存取權的電腦時，您就可以部署電話撥入式會議，以便他們可以使用公用交換的電話加入會議網路 (PSTN) 電話。

電話撥入式會議是選擇性功能，您可以設定當您部署 Lync Server 2013 會議。 雖然撥入式會議使用企業語音使用的相同 Lync Server 2013 元件，您可以部署電話撥入式會議，即使您未部署企業語音。

<div>


> [!NOTE]  
> 如果您部署電話撥入式會議，您必須將它部署中部署 Lync Server 2013 會議每個集區。 您不需要在每個集區中指派存取號碼，但是必須在每個集區中部署撥入功能。 這項要求支援錄製的名稱 」 功能，當使用者從一個集區加入 Lync Server 2013 會議的不同的集區中呼叫的存取號碼。



</div>

您必須在會議原則中啟用會議的撥入存取。根據預設，啟用撥入功能的會議會在會議邀請中包含下列資訊：

  - 可識別會議的數值會議 ID

  - 一個或多個 PSTN 存取號碼。

  - 電話撥入式會議設定] 頁面上，其中包含完整的存取號碼及其相關語言; 清單連結位置，以建立、 重設或解除封鎖個人識別碼 (Pin);與其他資訊，例如雙音多頻 (DTMF) 控制項。

電話撥入式會議同時支援企業和匿名使用者。 企業使用者具有 Active Directory 網域服務的認證和其組織內的 Lync Server 2013 帳戶。 匿名使用者在您組織內沒有企業認證。 在電話撥入式會議環境中，如果同盟協力廠商組織中的使用者使用 PSTN 連線至會議，則會視為匿名使用者。 與其他環境不同，電話撥入式會議並不會驗證同盟使用者。

企業使用者或會議主席欲參加已啟用撥入存取功能的會議時，要撥打其中一個會議存取號碼，然後系統會提示他們輸入會議 ID。 如果主席尚未加入會議，使用者可以輸入整合通訊 (UC) 分機 (或完整電話號碼) 和 PIN，或是等待主席准許加入會議。 會議召集人只要輸入 PIN 即可以主席身分加入會議。 前端伺服器使用完整的電話號碼或分機號碼和 pin 碼，的組合來唯一將企業使用者對應至 Active Directory 認證。 因此，在會議中，企業使用者已通過驗證，而且是以名稱識別。 企業使用者也可以擔任由召集人所預先定義的會議角色。

<div>


> [!NOTE]  
> 從 office IP 電話，或從 Lync Server 2013 或 Lync 2010 Attendant 撥入的企業使用者電話號碼不出現提示，因為他們已經通過驗證。



</div>

匿名使用者欲加入電話撥入式會議時，要撥打其中一個會議存取號碼，然後系統會提示他們輸入會議 ID。未經驗證的匿名使用者還會收到提示來記錄其名稱。記錄的名稱可識別會議中未經驗證的使用者。匿名使用者要等到至少有一位主席或已驗證使用者加入會議後，才能加入會議；此外，不能指派預先定義的角色給匿名使用者。

<div>


> [!NOTE]  
> 選擇不輸入電話號碼及 PIN 的企業使用者不會進行驗證。他們會收到提示，表示系統將記錄其名稱，並將其視為會議中的匿名使用者。



</div>

在排程階段，會議召集人可以選擇藉由關閉或鎖定會議，以限制會議的存取。在此情況下，系統會要求撥入式使用者接受驗證。如果撥入使用者驗證失敗或選擇不接受驗證，就會移轉至大廳，在那裡等候主席接受或拒絕他們加入會議，或是等候到逾時並中斷連線為止。撥入式使用者在等待獲准加入會議時，會聽到音樂聲。撥入式使用者在獲准加入會議之後，可以參與會議的音訊部分，並且可以利用電話鍵盤來執行複頻式訊號 (DTMF) 命令。撥入式主席可以執行 DTMF 命令來開啟或關閉參與者解除靜音的能力、鎖定或解除鎖定會議、准許大廳中的人員加入會議，以及開啟或關閉進入和退出宣告。主席也可以使用 DTMF 命令來准許大廳中的所有人員加入會議，這樣會變更會議的權限，允許任何人在後來加入。所有撥入式參與者都可以執行 DTMF 命令來聽取說明、聽取會議名冊，以及將自己靜音。

撥入式參與者 (不管他們是不是從 PSTN 撥入) 在會議期間會聽到個人宣告 (例如他們是否被靜音或解除靜音、已在錄製會議，或是有人在大廳等候)。

<div>


> [!NOTE]  
> 透過按下連結 (而非撥入) 方式來加入會議的參與者，不會聽到個人宣告。



</div>

</div>

<span> </span>

</div>

</div>

</div>

