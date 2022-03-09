modified_date: 2021-10-03 18:12:04 +0200
# Create the project
    /// Activate debug mode
    // short and long flags (-d, --debug) will be deduced from the field's name
    #[structopt(short, long)]
    debug: bool
    // etc ...
The raw patch to apply on a freshly created project using `cargo new --bin` can be found [here][patch-step1]
    setup_log(log::LevelFilter::Debug);
    setup_log(log::LevelFilter::Info);
The raw patch to apply on the previous step can be found [here][patch-step2]
    // ...
    Ok(args)
    Ok(args) => {
        log::info!("{:?}", args);
        exit_with_retcode(Ok(()))
    },
    Err(e) => {
        log::error!("Error while parsing arguments:\n\t{}", e);
        exit(e.get_retcode());
    }
The raw patch to apply on the previous step can be found [here][patch-step3]
    // ...
    if !args.mount_dir.exists() && !args.mount_dir.is_dir(){
        return Err(Errcode::ArgumentInvalid("mount"));
    }
    // ...
    ArgumentInvalid(&'static str),
    // Message to display when an argument is invalid
    Errcode::ArgumentInvalid(element) => write!(f, "ArgumentInvalid: {}", element),
    // ...
The raw patch to apply on the previous step can be found [here][patch-step4]
[patch-step1]: https://github.com/litchipi/crabcan/commit/step1.diff
[patch-step2]: https://github.com/litchipi/crabcan/commit/step2.diff
[patch-step3]: https://github.com/litchipi/crabcan/commit/step3.diff
[patch-step4]: https://github.com/litchipi/crabcan/commit/step4.diff