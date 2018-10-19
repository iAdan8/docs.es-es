---
title: Escenarios de negocio de ejemplo y casos de uso de aplicaciones sin servidor
description: Obtenga información sobre sin servidor con un enfoque práctico mediante el acceso a ejemplos que van desde el procesamiento de imágenes para servidores back-end móvil y las canalizaciones ETL.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: c38d1c6c4e04f3fa38946c97af5d94758b3ed6f7
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "49370204"
---
# <a name="serverless-business-scenarios-and-use-cases"></a><span data-ttu-id="6639b-103">Escenarios empresariales sin servidor y casos de uso</span><span class="sxs-lookup"><span data-stu-id="6639b-103">Serverless business scenarios and use cases</span></span>

<span data-ttu-id="6639b-104">Hay muchos casos de uso y escenarios para las aplicaciones sin servidor.</span><span class="sxs-lookup"><span data-stu-id="6639b-104">There are many use cases and scenarios for serverless applications.</span></span> <span data-ttu-id="6639b-105">Este capítulo incluye ejemplos que ilustran los distintos escenarios.</span><span class="sxs-lookup"><span data-stu-id="6639b-105">This chapter includes samples that illustrate the different scenarios.</span></span> <span data-ttu-id="6639b-106">Los escenarios incluyen vínculos a documentación relacionada y repositorios de código fuente público.</span><span class="sxs-lookup"><span data-stu-id="6639b-106">The scenarios include links to related documentation and public source code repositories.</span></span> <span data-ttu-id="6639b-107">Los ejemplos de este capítulo le permiten empezar a trabajar en su propia creación e implementación de soluciones sin servidor.</span><span class="sxs-lookup"><span data-stu-id="6639b-107">The samples in this chapter enable you to get started on your own building and implementing serverless solutions.</span></span>

## <a name="analyze-and-archive-images"></a><span data-ttu-id="6639b-108">Analizar y archivar las imágenes</span><span class="sxs-lookup"><span data-stu-id="6639b-108">Analyze and archive images</span></span>

<span data-ttu-id="6639b-109">Este ejemplo muestra el código (Azure Functions), los flujos de trabajo (aplicación lógica) y sin servidor eventos (Event Grid).</span><span class="sxs-lookup"><span data-stu-id="6639b-109">This sample demonstrates serverless events (Event Grid), workflows (Logic App), and code (Azure Functions).</span></span> <span data-ttu-id="6639b-110">También muestra cómo integrar con otro recurso, en este caso Cognitive Services para el análisis de la imagen.</span><span class="sxs-lookup"><span data-stu-id="6639b-110">It also shows how to integrate with another resource, in this case Cognitive Services for image analysis.</span></span>

<span data-ttu-id="6639b-111">Una aplicación de consola permite pasar un vínculo a una dirección URL en la web.</span><span class="sxs-lookup"><span data-stu-id="6639b-111">A console application allows you to pass a link to a URL on the web.</span></span> <span data-ttu-id="6639b-112">La aplicación publica la dirección URL como un mensaje de la cuadrícula de eventos.</span><span class="sxs-lookup"><span data-stu-id="6639b-112">The app publishes the URL as an event grid message.</span></span> <span data-ttu-id="6639b-113">En paralelo, una aplicación de función sin servidor y una aplicación lógica se suscriben al mensaje.</span><span class="sxs-lookup"><span data-stu-id="6639b-113">In parallel, a serverless function app and a logic app subscribe to the message.</span></span> <span data-ttu-id="6639b-114">La aplicación de función sin servidor, serializa la imagen en blob storage.</span><span class="sxs-lookup"><span data-stu-id="6639b-114">The serverless function app serializes the image to blob storage.</span></span> <span data-ttu-id="6639b-115">También almacena información en Azure Table Storage.</span><span class="sxs-lookup"><span data-stu-id="6639b-115">It also stores information in Azure Table Storage.</span></span> <span data-ttu-id="6639b-116">Los metadatos almacenan la dirección URL de imagen original y el nombre de la imagen de blob.</span><span class="sxs-lookup"><span data-stu-id="6639b-116">The metadata stores the original image URL and the name of the blob image.</span></span> <span data-ttu-id="6639b-117">La aplicación lógica se interactúa con la API de visión personalizada para analizar la imagen y crear un título generado por la máquina.</span><span class="sxs-lookup"><span data-stu-id="6639b-117">The logic app interacts with the Custom Vision API to analyze the image and create a machine-generated caption.</span></span> <span data-ttu-id="6639b-118">El título se almacena en la tabla de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6639b-118">The caption is stored in the metadata table.</span></span>

![Arquitectura de las imágenes de archivo y analizar](./media/image-processing-example.png)

<span data-ttu-id="6639b-120">Una aplicación independiente de página única (SPA) llama a una función sin servidor para obtener una lista de imágenes y los metadatos.</span><span class="sxs-lookup"><span data-stu-id="6639b-120">A separate single page application (SPA) calls a serverless function to get a list of images and metadata.</span></span> <span data-ttu-id="6639b-121">Para cada imagen, llama a otra función que proporciona los datos de imagen desde el archivo.</span><span class="sxs-lookup"><span data-stu-id="6639b-121">For each image, it calls another function that delivers the image data from the archive.</span></span> <span data-ttu-id="6639b-122">El resultado final es una galería con automática de subtítulos.</span><span class="sxs-lookup"><span data-stu-id="6639b-122">The final result is a gallery with automatic captions.</span></span>

![Galería de imágenes automatizadas](./media/automated-image-gallery.png)

<span data-ttu-id="6639b-124">El repositorio completo e instrucciones para compilar la aplicación lógica están disponibles aquí: [adherencia de cuadrícula de eventos](https://github.com/JeremyLikness/Event-Grid-Glue).</span><span class="sxs-lookup"><span data-stu-id="6639b-124">The full repository and instructions to build the logic app are available here: [Event grid glue](https://github.com/JeremyLikness/Event-Grid-Glue).</span></span>

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a><span data-ttu-id="6639b-125">Cliente móvil multiplataforma con Xamarin.Forms y funciones</span><span class="sxs-lookup"><span data-stu-id="6639b-125">Cross-platform mobile client using Xamarin.Forms and functions</span></span>

<span data-ttu-id="6639b-126">Vea cómo implementar una sencilla función de Azure sin servidor en el Portal Web de Azure o en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6639b-126">See how to implement a simple serverless Azure Function in the Azure Web Portal or in Visual Studio.</span></span> <span data-ttu-id="6639b-127">Cree un cliente con Xamarin.Forms que se ejecuta en Windows, iOS y Android.</span><span class="sxs-lookup"><span data-stu-id="6639b-127">Build a client with Xamarin.Forms that runs on Android, iOS, and Windows.</span></span> <span data-ttu-id="6639b-128">A continuación, se refina de la aplicación para que use JavaScript Object Notation (JSON) como un medio de comunicación entre el servidor y los clientes móviles con un back-end sin servidor.</span><span class="sxs-lookup"><span data-stu-id="6639b-128">The application is then refined to use JavaScript Object Notation (JSON) as a communication medium between the server and the mobile clients with a serverless back end.</span></span>

<span data-ttu-id="6639b-129">Para obtener más información, consulte [implementación de una simple función de Azure con un cliente de Xamarin.Forms](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)</span><span class="sxs-lookup"><span data-stu-id="6639b-129">For more information, see [Implementing a simple Azure Function with a Xamarin.Forms client](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)</span></span>

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a><span data-ttu-id="6639b-130">Generar un mosaico de foto con reconocimiento de imágenes sin servidor</span><span class="sxs-lookup"><span data-stu-id="6639b-130">Generate a photo mosaic with serverless image recognition</span></span>

<span data-ttu-id="6639b-131">El ejemplo usa Azure Functions y Microsoft Cognitive Services Custom Vision Service para generar un mosaico de fotografías de una imagen de entrada.</span><span class="sxs-lookup"><span data-stu-id="6639b-131">The sample uses Azure Functions and Microsoft Cognitive Services Custom Vision Service to generate a photo mosaic from an input image.</span></span> <span data-ttu-id="6639b-132">El modelo está entrenado para reconocer imágenes.</span><span class="sxs-lookup"><span data-stu-id="6639b-132">The model is trained to recognize images.</span></span> <span data-ttu-id="6639b-133">Cuando se carga una imagen, se reconoce la imagen y las búsquedas con Bing.</span><span class="sxs-lookup"><span data-stu-id="6639b-133">When an image is uploaded, it recognizes the image and searches with Bing.</span></span> <span data-ttu-id="6639b-134">La imagen original se puede volver a componer con los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6639b-134">The original image is recomposed using the search results.</span></span>

![Mosaico y la fotografía de ojo de Orlando](./media/orlando-eye-both.png)

<span data-ttu-id="6639b-136">Por ejemplo, puede entrenar el modelo con puntos de referencia de Orlando, por ejemplo, el efecto de ojos Orlando.</span><span class="sxs-lookup"><span data-stu-id="6639b-136">For example, you can train your model with Orlando landmarks, such as the Orlando Eye.</span></span> <span data-ttu-id="6639b-137">Custom Vision reconocerá una imagen del ojo Orlando, y la función creará un mosaico de foto formada por los resultados de búsqueda de imágenes de Bing para "Orlando ojos".</span><span class="sxs-lookup"><span data-stu-id="6639b-137">Custom Vision will recognize an image of the Orlando Eye, and the function will create a photo mosaic composed of Bing image search results for "Orlando Eye."</span></span>

<span data-ttu-id="6639b-138">Para obtener más información, consulte [generador de mosaic foto de Azure Functions](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/).</span><span class="sxs-lookup"><span data-stu-id="6639b-138">For more information, see [Azure Functions photo mosaic generator](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/).</span></span>

## <a name="migrate-an-existing-application-to-the-cloud"></a><span data-ttu-id="6639b-139">Migrar una aplicación existente a la nube</span><span class="sxs-lookup"><span data-stu-id="6639b-139">Migrate an existing application to the cloud</span></span>

<span data-ttu-id="6639b-140">Como se describe en los capítulos anteriores, es común a adoptar una arquitectura de N niveles para hospedar su aplicación en modo local.</span><span class="sxs-lookup"><span data-stu-id="6639b-140">As discussed in previous chapters, it's common to embrace an N-Tier architecture to host your application on-premises.</span></span> <span data-ttu-id="6639b-141">Aunque la migración de recursos "tal cual" uso de máquinas virtuales es la ruta de acceso menos riesgo a la nube, muchas compañías eligen usar la oportunidad para refactorizar sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6639b-141">Although migrating resources "as is" using virtual machines is the least risky path to the cloud, many companies choose to use the opportunity to refactor their applications.</span></span> <span data-ttu-id="6639b-142">Afortunadamente, la refactorización no tiene que ser un esfuerzo "todo o nada".</span><span class="sxs-lookup"><span data-stu-id="6639b-142">Fortunately, refactoring doesn't have to be an "all-or-nothing" effort.</span></span> <span data-ttu-id="6639b-143">De hecho, es posible migrar la aplicación, a continuación, reemplace por etapas componentes con equivalentes nativos en la nube.</span><span class="sxs-lookup"><span data-stu-id="6639b-143">In fact, it's possible to migrate your app then piecemeal replace components with cloud native counterparts.</span></span>

<span data-ttu-id="6639b-144">La aplicación utiliza la característica de los servidores proxy de Azure Functions para que la refactorización de un punto de conexión desde el código heredado en el entorno local a un punto de conexión sin servidor.</span><span class="sxs-lookup"><span data-stu-id="6639b-144">The application uses the proxies feature of Azure Functions to enable refactoring an endpoint from legacy on-premises code to a serverless endpoint.</span></span>

![Arquitectura de migración](./media/migration-architecture.png)

<span data-ttu-id="6639b-146">El proxy proporciona un único punto de conexión de API que se actualiza para enrutar las solicitudes individuales que se mueven a las funciones sin servidor.</span><span class="sxs-lookup"><span data-stu-id="6639b-146">The proxy provides a single API endpoint that is updated to reroute individual requests as they're moved into serverless functions.</span></span>

<span data-ttu-id="6639b-147">Puede ver un vídeo que le guía a través de la migración completa: [levantar y mover con Azure functions sin servidor](https://channel9.msdn.com/Events/Connect/2017/E102).</span><span class="sxs-lookup"><span data-stu-id="6639b-147">You can view a video that walks through the entire migration: [Lift and shift with serverless Azure functions](https://channel9.msdn.com/Events/Connect/2017/E102).</span></span> <span data-ttu-id="6639b-148">Obtener acceso al código de ejemplo: [traiga su propia aplicación](https://github.com/JeremyLikness/bring-own-app-connect-17).</span><span class="sxs-lookup"><span data-stu-id="6639b-148">Access the sample code: [Bring your own app](https://github.com/JeremyLikness/bring-own-app-connect-17).</span></span>

## <a name="parse-a-csv-file-and-insert-into-a-database"></a><span data-ttu-id="6639b-149">Analizar un archivo CSV e insertar en una base de datos</span><span class="sxs-lookup"><span data-stu-id="6639b-149">Parse a CSV file and insert into a database</span></span>

<span data-ttu-id="6639b-150">Extraer, transformar y carga (ETL) es una función empresarial común que integra sistemas diferentes.</span><span class="sxs-lookup"><span data-stu-id="6639b-150">Extract, Transform, and Load (ETL) is a common business function that integrates different systems.</span></span> <span data-ttu-id="6639b-151">Los enfoques tradicionales suelen implican configurar servidores dedicados de FTP, a continuación, implementar los trabajos programados para analizar los archivos y convertirlos para su uso empresarial.</span><span class="sxs-lookup"><span data-stu-id="6639b-151">Traditional approaches often involve setting up dedicated FTP servers then deploying scheduled jobs to parse files and translate them for business use.</span></span> <span data-ttu-id="6639b-152">Arquitectura sin servidor facilita el trabajo porque se puede activar un desencadenador cuando se cargue el archivo.</span><span class="sxs-lookup"><span data-stu-id="6639b-152">Serverless architecture makes the job easier because a trigger can fire when the file is uploaded.</span></span> <span data-ttu-id="6639b-153">Tareas de Azure Functions aparejos como ETL a través de su composición ideal de pequeños fragmentos de código que se centran en un problema específico.</span><span class="sxs-lookup"><span data-stu-id="6639b-153">Azure Functions tackles tasks like ETL through its ideal composition of small pieces of code that focus on a specific problem.</span></span>

![Arquitectura ETL](./media/csvimport.png)

<span data-ttu-id="6639b-155">Para el código fuente y un laboratorio práctico, vea [CSV importar laboratorio](https://github.com/JeremyLikness/azure-fn-file-process-hol).</span><span class="sxs-lookup"><span data-stu-id="6639b-155">For source code and a hands-on lab, see [CSV import lab](https://github.com/JeremyLikness/azure-fn-file-process-hol).</span></span>

## <a name="shorten-links-and-track-metrics"></a><span data-ttu-id="6639b-156">Acorte los vínculos y realizar un seguimiento de métricas</span><span class="sxs-lookup"><span data-stu-id="6639b-156">Shorten links and track metrics</span></span>

<span data-ttu-id="6639b-157">Herramientas reducir vínculo originalmente ayudado a codificar en resumen de las direcciones URL de twitter publicaciones para acomodar el límite de 140 caracteres.</span><span class="sxs-lookup"><span data-stu-id="6639b-157">Link shortening tools originally helped encode URLs in short twitter posts to accommodate the 140 character limit.</span></span> <span data-ttu-id="6639b-158">Ha crecido para abarcar varios usos, con más frecuencia para realizar un seguimiento de clics para el análisis.</span><span class="sxs-lookup"><span data-stu-id="6639b-158">They've grown to encompass several uses, most commonly to track click-throughs for analytics.</span></span> <span data-ttu-id="6639b-159">El escenario de shortener vínculo es una aplicación totalmente sin servidor que administra los vínculos y los informes de métricas.</span><span class="sxs-lookup"><span data-stu-id="6639b-159">The link shortener scenario is an entirely serverless application that manages links and reports metrics.</span></span>

<span data-ttu-id="6639b-160">Las funciones de Azure se usa para atender una aplicación de página única (SPA) que le permite pegar la dirección URL larga y generar direcciones URL breves.</span><span class="sxs-lookup"><span data-stu-id="6639b-160">Azure Functions is used to serve a Single Page Application (SPA) that allows you to paste the long URL and generate short URLs.</span></span> <span data-ttu-id="6639b-161">Las direcciones URL se etiquetan para realizar un seguimiento de las cosas como las campañas (temas) y los medios (por ejemplo, redes sociales que se registran los vínculos).</span><span class="sxs-lookup"><span data-stu-id="6639b-161">The URLs are tagged to track things like campaigns (topics) and mediums (such as social networks that the links are posted to).</span></span> <span data-ttu-id="6639b-162">Código corto se almacena en Azure Table Storage como la clave, con la dirección URL larga como el valor.</span><span class="sxs-lookup"><span data-stu-id="6639b-162">The short code is stored in Azure Table Storage as the key, with the long URL as the value.</span></span> <span data-ttu-id="6639b-163">Al hacer clic en el vínculo corto, otra función busca la dirección URL larga, envía una redirección y coloca la información sobre el evento en una cola.</span><span class="sxs-lookup"><span data-stu-id="6639b-163">When you click on the short link, another function looks up the long URL, sends a redirect, and places information about the event on a queue.</span></span> <span data-ttu-id="6639b-164">Otra función de Azure procesa la cola y coloca la información en Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="6639b-164">Another Azure Function processes the queue and places the information into Azure Cosmos DB.</span></span>

![Arquitectura de vínculo shortener](./media/link-shortener-architecture.png)

<span data-ttu-id="6639b-166">A continuación, puede crear un panel de Power BI para recopilar información sobre los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="6639b-166">You can then create a Power BI dashboard to gather insights about the data collected.</span></span> <span data-ttu-id="6639b-167">En el back-end, Application Insights proporciona métricas importantes.</span><span class="sxs-lookup"><span data-stu-id="6639b-167">On the back end, Application Insights provides important metrics.</span></span> <span data-ttu-id="6639b-168">Telemetría incluye cuánto tarda el usuario medio redirigir y cuánto tarda en obtener acceso a Azure Table Storage.</span><span class="sxs-lookup"><span data-stu-id="6639b-168">Telemetry includes how long it takes for the average user to redirect and how long it takes to access Azure Table Storage.</span></span>

![Ejemplo de Power BI](./media/power-bi-example.png)

<span data-ttu-id="6639b-170">El repositorio de shortener vínculo completo con instrucciones está disponible aquí: [reductor de URL sin servidor](https://github.com/jeremylikness/serverless-url-shortener).</span><span class="sxs-lookup"><span data-stu-id="6639b-170">The full link shortener repository with instructions is available here: [Serverless URL shortener](https://github.com/jeremylikness/serverless-url-shortener).</span></span> <span data-ttu-id="6639b-171">Puede leer acerca de una versión simplificada aquí: [el almacenamiento de Azure para aplicaciones .NET sin servidor en cuestión de minutos](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/).</span><span class="sxs-lookup"><span data-stu-id="6639b-171">You can read about a simplified version here: [Azure Storage for serverless .NET apps in minutes](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/).</span></span>

## <a name="verify-device-connectivity-using-a-ping"></a><span data-ttu-id="6639b-172">Comprobar la conectividad de dispositivo mediante un ping</span><span class="sxs-lookup"><span data-stu-id="6639b-172">Verify device connectivity using a ping</span></span>

<span data-ttu-id="6639b-173">El ejemplo consta de un centro de IoT de Azure y una función de Azure.</span><span class="sxs-lookup"><span data-stu-id="6639b-173">The sample consists of an Azure IoT Hub and an Azure Function.</span></span> <span data-ttu-id="6639b-174">Un mensaje nuevo en el centro de IoT desencadena la función de Azure.</span><span class="sxs-lookup"><span data-stu-id="6639b-174">A new message on the IoT Hub triggers the Azure Function.</span></span> <span data-ttu-id="6639b-175">El código sin servidor envía el mismo mensaje contenido al dispositivo que lo envió.</span><span class="sxs-lookup"><span data-stu-id="6639b-175">The serverless code sends the same message content back to the device that sent it.</span></span> <span data-ttu-id="6639b-176">El proyecto tiene toda la configuración de implementación y el código necesaria para la solución.</span><span class="sxs-lookup"><span data-stu-id="6639b-176">The project has all the code and deployment configuration needed for the solution.</span></span>

<span data-ttu-id="6639b-177">Para obtener más información, consulte [ping de Azure IoT Hub](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/).</span><span class="sxs-lookup"><span data-stu-id="6639b-177">For more information, see [Azure IoT Hub ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/).</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="6639b-178">Recursos recomendados</span><span class="sxs-lookup"><span data-stu-id="6639b-178">Recommended resources</span></span>

* [<span data-ttu-id="6639b-179">Generador de mosaic de Azure Functions foto</span><span class="sxs-lookup"><span data-stu-id="6639b-179">Azure Functions photo mosaic generator</span></span>](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/)
* [<span data-ttu-id="6639b-180">Ping de Azure IoT Hub</span><span class="sxs-lookup"><span data-stu-id="6639b-180">Azure IoT Hub ping</span></span>](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/)
* [<span data-ttu-id="6639b-181">Almacenamiento de Azure para aplicaciones .NET sin servidor en cuestión de minutos</span><span class="sxs-lookup"><span data-stu-id="6639b-181">Azure Storage for serverless .NET apps in minutes</span></span>](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/)
* [<span data-ttu-id="6639b-182">Traiga su propia aplicación</span><span class="sxs-lookup"><span data-stu-id="6639b-182">Bring your own app</span></span>](https://github.com/JeremyLikness/bring-own-app-connect-17)
* [<span data-ttu-id="6639b-183">Laboratorio de importación CSV</span><span class="sxs-lookup"><span data-stu-id="6639b-183">CSV import lab</span></span>](https://github.com/JeremyLikness/azure-fn-file-process-hol)
* [<span data-ttu-id="6639b-184">Pegado de cuadrícula de eventos</span><span class="sxs-lookup"><span data-stu-id="6639b-184">Event grid glue</span></span>](https://github.com/JeremyLikness/Event-Grid-Glue)
* [<span data-ttu-id="6639b-185">Implementación de una simple función de Azure con un cliente de Xamarin.Forms</span><span class="sxs-lookup"><span data-stu-id="6639b-185">Implementing a simple Azure Function with a Xamarin.Forms client</span></span>](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)
* [<span data-ttu-id="6639b-186">Levantar y mover con Azure functions sin servidor</span><span class="sxs-lookup"><span data-stu-id="6639b-186">Lift and shift with serverless Azure functions</span></span>](https://channel9.msdn.com/Events/Connect/2017/E102)
* [<span data-ttu-id="6639b-187">Reductor de URL sin servidor</span><span class="sxs-lookup"><span data-stu-id="6639b-187">Serverless URL shortener</span></span>](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
<span data-ttu-id="6639b-188">[Anterior](orchestration-patterns.md)
[Siguiente](serverless-conclusion.md)</span><span class="sxs-lookup"><span data-stu-id="6639b-188">[Previous](orchestration-patterns.md)
[Next](serverless-conclusion.md)</span></span>