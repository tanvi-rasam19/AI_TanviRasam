function generateVideo(query):
    concept = retrieveFromKnowledgeGraph(query)
    slides, script = AI_Module(concept)
    formatted = formatSlidesAndScript(slides, script)
    manimCode = convertToManim(formatted)
    video = renderVideo(manimCode)
    store(video)
    return video
