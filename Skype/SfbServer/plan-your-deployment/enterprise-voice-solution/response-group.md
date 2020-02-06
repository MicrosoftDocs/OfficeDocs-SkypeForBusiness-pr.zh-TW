---
title: 規劃商務用 Skype Server 中的回應群組應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: 規劃商務用 Skype Server Enterprise Voice 中的回應群組，可讓您設定呼叫路由至使用者群組。 包括音訊檔需求。
ms.openlocfilehash: ec0bbe0e02fd7b4f027f8c2e57784c402aa0f039
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802483"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>規劃商務用 Skype Server 中的回應群組應用程式

規劃商務用 Skype Server Enterprise Voice 中的回應群組，可讓您設定呼叫路由至使用者群組。 包括音訊檔需求。

如果您的組織有一組人接聽並管理特定類型的通話（例如客戶服務、內部說明服務台或部門的一般電話支援），您可以部署回應群組應用程式來管理這些呼叫類型。 回應群組應用程式會將來電路由並列隊給指定的人員（稱為代理者）。 您可以增加電話支援服務的使用，並使用回應群組來減少執行這些服務的額外負荷。

當來電者呼叫回應群組時，通話會根據查尋群組或來電者對互動式語音回應（IVR）問題的答案來傳送給代理程式。 回應群組應用程式會使用標準的回應群組路由方法，將呼叫路由至下一個可用的代理程式。 支援的呼叫路由方法包括串列、最長閒置、並行、迴圈和傳送路線（也就是，所有的代理程式都是在每次撥入通話時呼叫，不論其目前的狀態為何）。

如果沒有可用的代理，通話會一直保留在佇列中，直到有可用的代理程式。 在佇列中，來電者會聽到音樂，直到可用的代理程式接受通話。 如果佇列已滿，或通話在佇列中超時，來電者可能會聽到訊息，然後中斷連線或傳送到不同的目的地，例如不同的電話號碼或語音信箱。 當代理程式接受來電時，呼叫者可能也可能無法看到代理人的身分識別，視系統管理員設定回應群組的方式而定。 Agent 可以是正式的，這表示他們必須先登入群組，才能接受路由到群組的呼叫，或者是非正式的，這表示它們不會登入和登出群組以接受通話。

> [!NOTE]
> 只有內部部署使用者可以使用代理程式。 如果代理程式是從內部部署移至線上，回應群組呼叫將不會路由至該代理程式。

> [!NOTE]
> 回應群組應用程式使用名為 [相符] 的內部服務來排隊通話，並尋找可用的代理程式。 每個執行回應群組應用程式的電腦都會執行相符的服務，但一次只能有一個相符的服務，而其他則是被動的。 如果在未計畫的停機期間，使用中的 [相符] 使服務變為無法使用，其中一個被動的相符，就會變成作用中。 回應群組應用程式最能確保呼叫路由和佇列繼續不間斷地進行。 不過，當相符的服務轉換發生時，任何在該時間傳輸的呼叫都會遺失。 例如，如果您的轉換是由於前端伺服器即將停機而引起，則目前由作用中的 Match 所處理的任何呼叫都會在該前端伺服器上執行的服務也會遺失。

## <a name="response-group-workflows"></a>回應群組工作流程

工作流程會定義撥打電話到某人接聽來電之時間的通話行為。 工作流程會指定要用來進行通話的佇列，並指定用來進行查尋群組的傳送方法，或是用於互動式回應群組的問題與解答。 工作流程也會定義設定，例如 [歡迎] 訊息、[等候音樂]、[上班時間] 和 [假日]。

> [!NOTE]
> 您必須先建立代理群組和佇列，才能建立使用它們的工作流程。

## <a name="management-of-response-groups"></a>回應群組的管理

在商務用 Skype Server 中，有兩個管理角色可供管理回應群組： [回應群組管理員] 與 [回應群組管理員]。 回應群組管理員可以管理任何回應群組的任何方面。 回應群組管理員只能管理特定的部分，而且只能管理自己擁有的回應群組。 Manager 角色可協助您降低系統管理成本，因為您可以將特定回應群組的有限責任委派給任何已啟用企業語音的使用者。 請注意，使用者可以同時是回應群組管理員與回應群組系統管理員。

為了適應 Manager 角色，回應群組應用程式會使用受管理或未受管理的**工作流程類型**。 下表說明受管理和未受管理的回應群組。

**受管理和未受管理的回應群組**

|**回應群組類型**|**說明**|
|:-----|:-----|
|管  <br/> | 未受管理的回應群組沒有已指派的管理員。 只有回應群組管理員可以設定這些回應群組。 <br/>  多個未受管理的回應群組可以共用 [佇列] 或 [代理] 群組。 <br/>  當您將回應群組從先前的版本遷移到商務用 Skype Server 之後，該類型就會設定為 [未管理]。 <br/> |
|被  <br/> | 回應群組管理員可以設定受管理回應群組的任何方面。 <br/>  回應群組管理員無法查看或修改未明確指派給他們的回應群組。 <br/>  回應群組管理員只能針對明確指派給他們的回應群組設定部分設定。 <br/>  受管理的回應群組無法與任何其他回應群組、託管或未受管理的人共用任何佇列或代理群組。 <br/> |

下表說明回應群組管理員可以對指派給他們的回應群組執行哪些動作。

**回應群組管理員功能**

|**可以設定：**|**可以建立、刪除或設定：**|**不**|
|:-----|:-----|:-----|
| 代理程式 <br/>  歡迎訊息 <br/>  回應群組名稱 <br/>  說明 <br/>  顯示數位 <br/>  商務時間 <br/>  等候音樂 <br/>  狀態（有效/非使用中） <br/>  查尋群組工作流程或互動式語音回應（IVR）工作流程 <br/> | 代理群組 <br/>  佇列 <br/>  假日集 <br/> | 建立或刪除任何類型的工作流程 <br/>  修改核心回應群組設定，例如： **SIP URI**、**電話號碼**或**工作流程類型**。  <br/> |

回應群組管理員可以使用下列工具來管理其指定的回應群組。

- 商務用 Skype Server 的 [控制台]

    > [!NOTE]
    > 回應群組管理員只能使用此工具管理回應群組設定。 系統管理員不提供其他商務用 Skype 伺服器設定。

- 回應群組設定工具

- 商務用 Skype Server 管理命令介面

回應群組很適合部門或工作組環境（如需詳細資訊，請參閱[回應群組的容量規劃](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)），而且可以在全新的電話安裝中部署。 它支援來自企業語音部署和來自本機電信公司網路的傳入通話。 代理程式可以使用商務用 Skype、Lync 2013、Lync 2010、Lync 2010 助理或 Lync Phone Edition，進行傳送給他們的通話。

## <a name="deployment-and-requirements"></a>部署與需求

當您部署企業語音時，系統會自動啟用回應群組應用程式。

### <a name="hardware-and-software-requirements"></a>硬體及軟體需求

回應群組應用程式具有相同的硬體需求、作業系統需求和軟體先決條件（作為前端伺服器）。

如果您使用 Windows Media Audio （.wma）檔案來取得回應群組的音樂與宣告，所有前端伺服器或執行回應群組應用程式的標準版伺服器，都必須針對執行 Windows 的伺服器安裝 Windows Media 格式執行時間伺服器 2008 R2 或適用于執行 Windows Server 2012 或 Windows Server 2012 R2 之伺服器的 Microsoft 媒體基礎。 針對 Windows Server 2008 R2，Windows Media 格式執行時間已安裝為 Windows 桌面體驗的一部分。

回應群組使用**語言套件**來支援文字轉換語音和語音辨識。 當您設定郵件時，會使用這些語音技術，例如歡迎訊息及其他提示，以及互動式語音回應（IVR）問題與解答。 根據預設，在您部署商務用 Skype Server 時，會安裝26個支援的語言套件。

### <a name="port-requirements"></a>埠需求

回應群組應用程式使用下列埠：

- SIP 偵聽要求的**埠 5071**

- Interserver 通訊的**埠 8404**

    > [!NOTE]
    > 這個埠是用於相符的服務，而且當回應群組應用程式部署在擁有多個前端伺服器的池中時，就是必要的。

   > [!NOTE]
   > 這些埠是預設的設定，您可以使用**CsApplicationServer** Cmdlet 變更這些設定。 如需此 Cmdlet 的詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。

### <a name="audio-file-requirements"></a>音訊檔需求

回應群組應用程式支援波形（.wav）檔案格式和 Windows Media 音訊（.wma）檔案格式，以取得回應群組訊息、等候音樂或互動式語音回應（IVR）問題。

Windows Media 音訊檔案格式要求 Windows Media 格式執行時間已安裝在執行 Windows Server 2008 R2 和 Windows Server 2008 的前端伺服器上。 如需詳細資訊，請參閱本節前面的「軟體需求」。

#### <a name="supported-wave-file-formats"></a>支援的 Wave 檔案格式

所有的 wave 檔案必須符合下列需求：

- 8位或16位檔案

- 線性脈衝程式碼調製（LPCM）、法律或 mu-定律格式

- 單聲道或身歷聲

- 4MB 或更低

為了獲得波形檔案的最佳效能，建議使用 16 kHz、單聲道、16位波檔案。

#### <a name="supported-windows-media-audio-file-formats"></a>支援的 Windows Media 音訊檔案格式

如果您使用的是 Windows Media 音訊檔，請考慮使用低傳輸率，並在 [載入] 底下驗證系統的效能。

您可以使用 Microsoft Expression 編碼器4將檔案轉換成 Windows Media 音訊格式。 若要下載運算式編碼器4， [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843)請參閱。

### <a name="response-group-configuration-tool-requirements"></a>回應群組設定工具需求

[回應群組設定] 工具支援下表所述的作業系統與網頁瀏覽器混合。

> [!NOTE]
> 支援32位或64位版本的作業系統。 僅支援32位版本的 Internet Explorer。

**支援的作業系統與網頁瀏覽器**

|**作業系統**|**網頁瀏覽器**|
|:-----|:-----|
|Windows Vista （含 Service Pack （SP）2）  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 （原生模式）  <br/> Internet Explorer 9 （原生模式）  <br/> |
|Windows 7  <br/> Windows 7 Service Pack 1  <br/> |Internet Explorer 8 （原生模式）  <br/> Internet Explorer 9 （原生模式）  <br/> |
|Windows Server 2008 Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 （原生模式）  <br/> Internet Explorer 9 （原生模式）  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 Service Pack 1  <br/> |Internet Explorer 8 （原生模式）  <br/> Internet Explorer 9 （原生模式）  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>回應群組代理程式主控台

[代理程式主控台] 支援下表所述的作業系統與網頁瀏覽器混合。

> [!NOTE]
> 支援32位或64位版本的作業系統。 僅支援32位版本的 Internet Explorer。

**支援的作業系統與網頁瀏覽器**

|**作業系統**|**網頁瀏覽器**|
|:-----|:-----|
|Windows Vista （含 Service Pack （SP）2）  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 （原生模式）  <br/> Internet Explorer 9 （原生模式）  <br/> |
|Windows 7  <br/> Windows 7 Service Pack 1  <br/> |Internet Explorer 8 （原生模式）  <br/> Internet Explorer 9 （原生模式）  <br/> Firefox 10。0  <br/> Chrome 18。0  <br/> |
|Windows Server 2008 Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 （原生模式）  <br/> Internet Explorer 9 （原生模式）  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 Service Pack 1  <br/> |Internet Explorer 8 （原生模式）  <br/> Internet Explorer 9 （原生模式）  <br/> Firefox 10。0  <br/> Chrome 18。0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>用戶端支援

回應群組應用程式支援下列用戶端：

- 商務用 Skype 桌面用戶端

- Lync 2013 桌面用戶端

- Lync 2010 桌面用戶端

- Lync 2010 助理

- Office 通訊伺服器 2007 R2 助理

- Lync Phone Edition

> [!NOTE]
> Lync 行動用戶端不支援回應群組應用程式。

您可以使用的特定用戶端取決於您所使用的回應群組使用者類型：

- **呼叫**者可以使用前面所列的任何用戶端呼叫回應群組，並使用標準電話透過公用交換電話網絡（PSTN）撥打電話。

- **非正式代理**（不登入和登出群組即可接受呼叫）的代理可以使用助理、Lync 或 Lync Phone Edition 接受通話。 當使用者使用下列其中一個用戶端登入商務用 Skype 伺服器時，就會自動登入他們的群組。

- **正式代理**（必須登入或登出其群組才能接受呼叫）可以接受呼叫，方法是使用商務用 Skype，然後從功能表項目存取代理程式主控台，或是使用 [助理] 直接從 Internet Explorer 存取代理程式主控台。

## <a name="capacity-planning"></a>容量規劃

下表說明您可以用來做為容量規劃需求基礎的 [回應群組] 使用者模型。

> [!NOTE]
> 下表中的數位假設您針對所有回應群組音訊檔案使用 16 kHz、單聲道、16位波（.wav）檔案。 如果您使用其他檔案格式（例如，Windows Media Audio （.wma）），這些數位可能會有所不同。

> [!IMPORTANT]
> 請記住，對於災難復原容量規劃，配對池的每個池都應該能夠處理兩個池中所有回應群組的工作量。

**回應群組使用者模型**

|**衡量**|**每個企業版<br/>池（含8個前端伺服器）**|**每個標準版 server**|
|:-----|:-----|:-----|
|每秒來電數  <br/> |位  <br/> |2  <br/> |
|連線到 IVR 或 MoH 的並行呼叫  <br/> |480  <br/> |60  <br/> |
|並行匿名會話（無 IM）  <br/> |224  <br/> |28  <br/> |
|並行匿名會話（與 IM）  <br/> |64  <br/> |型  <br/> |
|使用中的代理程式（正式與非正式）  <br/> |2400  <br/> |2400  <br/> |
|查尋群組的數目  <br/> |800  <br/> |800  <br/> |
|IVR 群組數（使用語音辨識）  <br/> |400  <br/> |400  <br/> |


