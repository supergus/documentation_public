.. _pub_docs_glossary_top-label:

Glossary
========

Liveline Technologies employs advanced concepts from controls engineering and artificial intelligence.
Terminology from one of those fields may not always be clear to practitioners in the other.
Here we define some common terms you may encounter when working with our products.

|

.. glossary::
    :sorted:

    artificial intelligence
    AI
        We feel a bit guilty using this term, because most people assume this refers to a
        artificial general intelligence, or AGI, which does not yet exist, and may
        not ever be possible to create. A true AGI would be able to understand or learn any task
        that a human can perform, and could possibly attain self-awareness or consciousness.
        Liveline Technologies employs advanced :term:`machine learning<machine learning>` techniques
        that are often described as "AI" in casual conversation.

    machine learning
    ML
        Unlike :term:`AGI<artificial intelligence>`, machine learning (ML) is very real.
        ML uses statistical models to learn from data, rather than being explicitly programmed to
        perform a specific task. Models can be extremely powerful, and their ability to learn subtle
        thing can sometimes feel like magic. In reality, it's just a form of very advanced statistics.

        Liveline Technologies makes extensive use of two of the three major fields within ML:
        `supervised learning <https://en.wikipedia.org/wiki/Supervised_learning>`_ and
        `reinforcement learning <https://en.wikipedia.org/wiki/Reinforcement_learning>`_.
        The third field is `unsupervised learning <https://en.wikipedia.org/wiki/Unsupervised_learning>`_,
        which is less commonly used within the Liveline technology stack.

    controller performance
        Controls engineers usually mean something very specific when they talk about evaluating the
        performance of a controller. There is a
        `well-developed body <https://en.wikipedia.org/wiki/Control_theory>`_
        of theoretical and applied knowledge
        around this topic.

        Performance may consider the time response of the controlled system as
        measured by rise time, peak overshoot, settling time, etc. It may also consider robustness
        in the face of uncertain or noisy measurements. Such metrics are common when implementing,
        for example, a classic `PID controller <https://en.wikipedia.org/wiki/PID_controller>`_.

        In the case of controllers based on trained :term:`machine learning<machine learning>` models,
        we may be interested in additional performance metrics, such as level of activity (how
        frequently the controllers want to change equipment parameters) and drift of controller performance
        over various timescales.

        We evaluate controller performance using a :term:`Liveline Test Harness<Liveline Test Harness>`
        that is configured according to your performance requirements.

    Liveline Test Harness
    LTH
        A standardized suite of metrics to assess
        :term:`controller performance<controller performance>`.
        Metrics will be adjusted based on the requirements of a particular production environment.
        The metrics may include typical items from classical
        `controls theory <https://en.wikipedia.org/wiki/Control_theory>`_,
        along with items that are unique to implementing controls via
        :term:`machine learning models<machine learning models>`.

    reinforcement learning
    RL
        An area of :term:`machine learning<machine learning>` concerned with how intelligent agents ought to
        take actions in an environment in order to maximize some notion of cumulative performance.

        At Liveline Technologies, our controllers are actually RL-based agents that are trained to "drive"
        a factory system. As part of our automated machine learning process, we create a model of your
        factory system, and our RL agents learn how to manipulate controllable variables to achieve desirable
        outcomes while avoiding negative things like exceeding maximum settings on machines.

        Typically, we create a factory model and controller agent for each combination of SKU and line or cell
        within a plant.

        Factory models are encrypted and stored in Liveline Physics Packages (LPP), and controller are
        encrypted and stored in Liveline Controls Packages (LCP).

    Liveline Physics Package
    LPP
        An encrypted software object that contains a trained model of factory physics, along
        with the feature engineering pipeline necessary to process raw data in batch or online modes.
        Typically we train one LPP for each combination of SKU and line or cell within your plant.
        Training is highly automated, and LPPs are "refreshed" as conditions change within the plant.

    Liveline Controls Package
    LCP
        An encrypted software object that contains a trained model to control
        equipment in a factory system.
        Typically we train one LCP for each combination of SKU and line or cell within your plant.
        Training is highly automated, and LCPs are "refreshed" as conditions change within the plant.

    Liveline Digital Controls Platform
    LDCP
        This is the basic digitization platform that allows us to implement factory controls.
        The technology stack is proprietary but built entirely on open-source technology.

    Liveline Data Quality Score
    LDQS
        A proprietary measure of how useful a particular chunk of factory data will be for training
        new models. DQS is continuously calculated while your plant runs normal production.
        We automatically select the most useful data for training our models.

A sonnet
--------

We asked `ChatGPT <https://en.wikipedia.org/wiki/ChatGPT>`_
to define :term:`machine learning<machine learning>` in the form of a Shakespearean sonnet.
This it what it returned:

        | Oh noble art of Machine Learning, so grand,
        | A gift of modern science to the hand,
        | Of engineers and coders, who impart
        | Its mysteries to machines, that they might stand
        | In excellence before all of mankind,
        | And do what once was thought beyond their might.
        |
        | With algorithms and models, they imbue
        | The power to learn, to make their own right
        | Decisions, with no need for human hand.
        | Thus, they evolve, with accuracy in sight,
        | And bring new solutions to our world's plight.
        |
        | Oh, how they sift through mountains of data,
        | With grace and speed, to find what we need.
        | Thus, do they make our lives so much brighter.
        |
        | And so, I sing the praises of this breed,
        | Of machines that learn, that we might succeed.
        |
        | --- ChatGPT, 9 February 2003
